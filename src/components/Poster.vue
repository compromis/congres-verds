<script setup>
import { onMounted } from 'vue'
import Parallax from 'parallax-js'

onMounted(() => {
  const scene = document.getElementById('scene')
  const parallaxInstance = new Parallax(scene)
})
</script>

<template>
<section class="poster">
    <div id="scene" class="scene">
      <img src="../images/layer-details.png" data-depth="0.2" alt="" class="layer layer-details" />
      <img src="../images/layer-flower.png" data-depth="0.3" alt="" class="layer layer-flower" />
      <img src="../images/layer-photos-top.png" data-depth="0.4" alt="" class="layer layer-photos-top" />
      <img src="../images/layer-photos-bottom.png" data-depth="0.5" alt="" class="layer layer-photos-bottom" />
      <img src="../images/layer-text.png" data-depth="0.6" alt="L'hora de les i els Verds" class="layer layer-text" />
    </div>
</section>
</template>

<style lang="scss">
  .poster {
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .scene {
    position: relative;
    width: 842px;
    height: 700px;
    margin: 2rem;

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
