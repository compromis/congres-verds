<template>
  <footer class="conference-info">
    <MarqueeText :duration="20" :repeat="4">
      <div class="scroll">
        <span class="scroll-title">RESPOSTES VERDES EN TEMPS D'EMERGÈNCIES</span>
        <span class="scroll-date">7 DE MAIG 10:00H</span>
        <span class="scroll-venue">COMPLEX CULTURAL LA PETXINA. VALÈNCIA</span>
      </div>
    </MarqueeText>
  </footer>
</template>

<script setup>
import MarqueeText from 'vue-marquee-text-component'
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
  z-index: 1000;
}

.scroll {
  padding: .5rem;
  display: flex;
  gap: 2rem;

  &-title {
    --to-color: var(--pine);
    animation: flash 3s infinite;
  }

  &-date {
    animation: flash 3s infinite;
    animation-delay: 1s;
  }

  &-venue {
    animation: flash 3s infinite;
    animation-delay: 2s;
  }
}

@keyframes flash {
  0% {
    color: var(--to-color, var(--green));
  }
  15% {
    color: var(--white);
  }
  33% {
    color: var(--to-color, var(--green));
  }
  100% {
    color: var(--to-color, var(--green));
  }
}
</style>