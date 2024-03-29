<script setup>
import { ref, onMounted } from 'vue'
import Parallax from 'parallax-js'
import PosterPages from './PosterPages.vue'
import LayerDetails from '@/images/layer-details.png'
import LayerFlower from '@/images/layer-flower.png'
import LayerPhotosTop from '@/images/layer-photos-top.png'
import LayerPhotosBottom from '@/images/layer-photos-bottom.png'
import LayerText from '@/images/layer-text.png'

onMounted(() => {
  const scene = document.getElementById('scene')
  const parallaxInstance = new Parallax(scene)
  page.value = window.location.hash
})

const page = ref(null)

const setPage = (value) => {
  page.value = '#' + value
  history.pushState({}, '', '#' + value)
}

if (typeof window !== "undefined") {
  window.onhashchange = () => {
    page.value = window.location.hash
  }
}

const closePage = () => {
  page.value = null
  history.replaceState(undefined, undefined, " ")
}
</script>

<template>
  <section class="poster">
      <div id="scene" class="scene">
        <img :src="LayerDetails" data-depth="0.2" alt="" class="layer layer-details" />
        <img :src="LayerFlower" data-depth="0.3" alt="" class="layer layer-flower" />
        <img :src="LayerPhotosTop" data-depth="0.4" alt="" class="layer layer-photos-top" />
        <img :src="LayerPhotosBottom" data-depth="0.5" alt="" class="layer layer-photos-bottom" />
        <img :src="LayerText" data-depth="0.6" alt="L'hora de les i els Verds" class="layer layer-text" />

        <div class="nav-item floats candidates d-none d-md-block" data-depth="0.3">
          <a href="#candidatures" @click.prevent="setPage('candidatures')">Candidatures</a>
        </div>
        <div class="nav-item floats documents d-none d-md-block" data-depth="0.4">
          <a href="#documents" @click.prevent="setPage('documents')">Documents</a>
        </div>
        <div class="nav-item floats info d-none d-md-block" data-depth="0.6" style="z-index: 10000">
          <a href="#info" @click.prevent="setPage('info')">Informació</a>
        </div>
        <div class="nav-item floats form d-none d-md-block" data-depth="0.5" style="z-index: 10000">
          <a href="https://docs.google.com/forms/d/e/1FAIpQLSel99LGY-hVoiVD9jQ_yel-TpkEln0AZ6PHH2ZBfUhSNtx3WA/viewform" target="_blank" rel="noopener">Registre</a>
        </div>
      </div>
      <div class="mobile-nav-items d-md-none">
        <div class="nav-item candidates">
          <a href="#candidatures" @click.prevent="setPage('candidatures')">Candidatures</a>
        </div>
        <div class="nav-item info">
          <a href="https://docs.google.com/forms/d/e/1FAIpQLSel99LGY-hVoiVD9jQ_yel-TpkEln0AZ6PHH2ZBfUhSNtx3WA/viewform" target="_blank" rel="noopener">Registre</a>
        </div>
        <div class="nav-item documents">
          <a href="#documents" @click.prevent="setPage('documents')">Documents</a>
        </div>
        <div class="nav-item info">
          <a href="#info" @click.prevent="setPage('info')">Informació</a>
        </div>
      </div>
      <PosterPages :page="page" @close="closePage" />
  </section>
</template>

<style lang="scss">
  .poster {
    min-height: calc(100vh - 8rem);
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;

    .nav-item {
      inset: 0;
      pointer-events: none;

      &.floats a {
        position: absolute;
      }

      a {
        display: block;
        background: var(--white);
        font-family: var(--font-headings);
        color: var(--black);
        border-radius: 100px;
        padding: .5rem 2rem;
        font-size: clamp(1.5rem, 4vw, 2.5rem);
        transition: .2s ease;
        pointer-events: all;

        &:hover {
          background: var(--yellow);
          text-decoration: none;
          transform: scale(1.1);
        }
      }

      &.candidates a {
        top: -3.5%;
        left: -11%;
      }

      &.documents a {
        top: -6.5%;
        right: -1%;
      }

      &.info a {
        bottom: -1%;
        right: 10%;
      }

      &.form a {
        bottom: 2%;
        left: 1%;
      }
    }
  }

  .mobile-nav-items {
    margin-bottom: 4rem;

    .nav-item {
      margin-bottom: 1rem;
      text-align: center;
    }
  }

  .scene {
    position: relative;
    width: 100%;
    height: auto;
    max-width: 842px;
    max-height: 700px;
    margin: 2rem;

    .layer {
      position: absolute;
      inset: 0;
      pointer-events: none;
      width: 100%;

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

  @media (max-width: 1100px) {
    .poster {
      min-height: auto;

      .nav-item {
        &.candidates a {
          left: 0;
        }
      }
    }
  }

  @media (min-width: 750px) {
    .scene .layer {
      max-height: calc(100vh - 14rem);
      object-fit: contain;
    }
  }
</style>
