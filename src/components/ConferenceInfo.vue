<template>
  <footer class="conference-info">
    <Vue3Marquee :duration="30">
      <div class="scroll">
        <span class="scroll-title">RESPOSTES VERDES EN TEMPS D'EMERGÈNCIES</span>
        <span class="scroll-date">7 DE MAIG</span>
        <span class="scroll-venue">10:00H. COMPLEX CULTURAL LA PETXINA. VALÈNCIA</span>
        <span class="scroll-title">RESPOSTES VERDES EN TEMPS D'EMERGÈNCIES</span>
        <span class="scroll-date">7 DE MAIG</span>
        <span class="scroll-venue">10:00H. COMPLEX CULTURAL LA PETXINA. VALÈNCIA</span>
      </div>
    </Vue3Marquee>
  </footer>
</template>

<script setup>
import { Vue3Marquee } from 'vue3-marquee'
import 'vue3-marquee/dist/style.css'
</script>

<style lang="scss" scoped>
.conference-info {
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  background: var(--yellow);
  color: var(--primary);
  font-size: 2.25rem;
  font-size: clamp(1.75rem, 3vw, 2.25rem);
  font-weight: bold;
}

.scroll {
  padding: .5rem;
  display: flex;
  gap: 2rem;

  &-title {
    animation: flash-pine 3s steps(4, end) infinite;
  }

  &-date {
    animation: flash 3s steps(4, end) infinite;
    animation-delay: 1s;
  }

  &-venue {
    animation: flash 3s steps(4, end) infinite;
    animation-delay: 2s;
  }
}

@keyframes flash {
  0% {
    color: var(--green);
  }
  15% {
    color: var(--white);
  }
  33% {
    color: var(--green);
  }
  100% {
    color: var(--green);
  }
}

@keyframes flash-pine {
  0% {
    color: var(--pine);
  }
  15% {
    color: var(--white);
  }
  33% {
    color: var(--pine);
  }
  100% {
    color: var(--pine);
  }
}
</style>