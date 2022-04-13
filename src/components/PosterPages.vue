<script setup>
import PageModal from './PageModal.vue'
import PageCandidatures from './PageCandidatures.vue'
import PageDocuments from './PageDocuments.vue'
import PageInfo from './PageInfo.vue'

defineProps({
  page: {
    type: String
  }
})

defineEmits(['close'])
</script>

<template>
  <div class="pages">
    <transition name="page">
      <PageModal id="candidatures" title="Candidatures" v-if="page === '#candidatures'" @close="$emit('close')">
        <PageCandidatures />
      </PageModal>
    </transition>
    <transition name="page">
      <PageModal id="documents" title="Documents" v-if="page === '#documents'" @close="$emit('close')">
        <PageDocuments />
      </PageModal>
    </transition>
    <transition name="page">
      <PageModal id="info" title="III Congrés dels Verds" v-if="page === '#info'" @close="$emit('close')">
        <PageInfo />
      </PageModal>
    </transition>
    <div class="backdrop d-md-none" @click="$emit('close')" v-if="page"></div>
  </div>
</template>

<style lang="scss">
.page-enter-active,
.page-leave-active {
  transition: 0.5s ease;
}

.page-enter-from,
.page-leave-to {
  transform: translateX(100%) scale(0.75) rotate(25deg);
}

.backdrop {
  position: fixed;
  inset: 0;
  z-index: 10000;
  background: rgba(0, 0, 0, .5);
}

@media (max-width: 750px) {
  .page-enter-from,
  .page-leave-to {
    opacity: 0;
    transform: translateY(100%) scale(.5) rotate(25deg);
  }
}
</style>