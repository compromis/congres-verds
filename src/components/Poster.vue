<script setup>
import { ref, onMounted } from 'vue'

const scene = ref(null)
onMounted(() => {
  console.log('mounted', scene)
})
</script>

<template>
  <section ref="scene" class="poster">
    <img src="../images/layer-details.png" alt="" class="layer layer-details" />
    <img src="../images/layer-flower.png" alt="" class="layer layer-flower" />
    <img src="../images/layer-photos-top.png" alt="" class="layer layer-photos-top" />
    <img src="../images/layer-photos-bottom.png" alt="" class="layer layer-photos-bottom" />
    <img src="../images/layer-text.png" alt="L'hora de les i els Verds" class="layer layer-text" />
  </section>
</template>

<style lang="scss">
  .poster {
    position: relative;
    width: 842px;
    height: 700px;
    margin: 0 auto;

    .layer {
      position: absolute;
      inset: 0;

      &-text {
        z-index: 50;
      }

      &-flower {
        z-index: 30;
      }

      &-photos-top {
        z-index: 20;
      }

      &-photos-bottom {
        z-index: 60;
      }

      &-details {
        z-index: 10;
      }
    }
  }
</style>
