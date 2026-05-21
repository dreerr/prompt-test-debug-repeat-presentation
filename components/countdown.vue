<template>
  <div class="timer-wrap">
        <div
            ref="timerEl"
            :class="['timer', { overtime: isOvertime }]"
            @click="onTimerClick"
            @pointerdown="onPressStart"
            @pointerup="onPressEnd"
            @pointerleave="onPressEnd"
            @pointercancel="onPressEnd"
        >
            {{ formattedTime }}
        </div>
    </div>
</template>
<script setup>
import { and } from '@vueuse/math'
import { useNav } from '@slidev/client/composables/useNav.ts'
import { useSlideContext } from '@slidev/client/context.ts'
import { resolvedClickMap } from '@slidev/client/modules/v-click.ts'
import { ref, computed, onMounted, onUnmounted } from 'vue'
import { watch } from 'vue'
const props = defineProps({
    minutes: {
        type: Number,
        default: 10
    },
    seconds: {
        type: Number,
        default: 0
    },
    autostart: {
        type: Boolean,
        default: false
    }
})
const totalSeconds = props.minutes * 60 + props.seconds
const elapsed = ref(0)
const hasStarted = ref(false)
const userPaused = ref(false)
const longPressTriggered = ref(false)
const timerEl = ref()
const isOvertime = computed(() => elapsed.value >= totalSeconds)

const { $slidev, $renderContext, $route } = useSlideContext()
const { isPrintMode } = useNav()

const noPlay = computed(() => isPrintMode.value || !['slide', 'presenter'].includes($renderContext.value))
const matchRoute = computed(() => !!$route && $route.no === $slidev?.nav.currentSlideNo)
const matchClick = computed(() => !!timerEl.value && (resolvedClickMap.get(timerEl.value)?.isShown?.value ?? true))
const matchRouteAndClick = and(matchRoute, matchClick)

const formattedTime = computed(() => {
    if (!isOvertime.value) {
        const remaining = totalSeconds - elapsed.value
        const mm = String(Math.floor(remaining / 60)).padStart(2, '0')
        const ss = String(remaining % 60).padStart(2, '0')
        return `${mm}:${ss}`
    }

    const overtime = elapsed.value - totalSeconds
    const mm = String(Math.floor(overtime / 60)).padStart(2, '0')
    const ss = String(overtime % 60).padStart(2, '0')
    return `+${mm}:${ss}`
})

let timer
let longPressTimeout
const LONG_PRESS_MS = 600

const stopTimer = () => {
    if(timer) {
        clearInterval(timer)
        timer = null
    }
}

const startTimer = () => {
    if(timer) {
        return
    }

    hasStarted.value = true
    timer = setInterval(() => {
        elapsed.value++
    }, 1000)
}

const onPressStart = () => {
    onPressEnd()
    longPressTriggered.value = false
    longPressTimeout = setTimeout(() => {
        longPressTriggered.value = true
        elapsed.value = 0
        hasStarted.value = false
        userPaused.value = true
        stopTimer()
    }, LONG_PRESS_MS)
}

const onPressEnd = () => {
    if(longPressTimeout) {
        clearTimeout(longPressTimeout)
        longPressTimeout = null
    }
}

const onTimerClick = () => {
    if(longPressTriggered.value) {
        longPressTriggered.value = false
        return
    }

    if(timer) {
        userPaused.value = true
        stopTimer()
        return
    }

    if(noPlay.value || !matchRouteAndClick.value) {
        return
    }

    userPaused.value = false
    startTimer()
}

onMounted(() => {
    watch(matchRouteAndClick, () => {
        if(noPlay.value || !matchRouteAndClick.value) {
            stopTimer()
            return
        }

        if(!userPaused.value && (hasStarted.value || props.autostart)) {
            startTimer()
        }
    }, { immediate: true })
})

onUnmounted(() => {
    onPressEnd()
    stopTimer()
})
</script>

<style scoped>
.timer {
    font-size: 6rem;
    font-weight: 600;
    font-variant-numeric: tabular-nums;
    cursor: pointer;
}

.timer.overtime {
    color: #e11d48;
}
</style>
