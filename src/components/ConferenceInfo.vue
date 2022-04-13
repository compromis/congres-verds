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
