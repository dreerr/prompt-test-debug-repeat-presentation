<template>
  <div class="timer-wrap">
        <div :class="['timer', { overtime: isOvertime }]" @click="resetTimer">{{ formattedTime }}</div>
</div>
</template>
<script setup>
import { ref, computed, onMounted, onUnmounted } from 'vue'
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
const isOvertime = computed(() => elapsed.value >= totalSeconds)

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
const resetTimer = () => {
    elapsed.value = 0
    hasFinishedBeeped.value = false
    if(!timer) {
        startTimer()
    }
}

onMounted(() => {
  if(props.autostart) {
    startTimer()
  }
})

const startTimer = () => {
    timer = setInterval(() => {
        elapsed.value++
    }, 1000)
}

onUnmounted(() => {
    clearInterval(timer)
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
