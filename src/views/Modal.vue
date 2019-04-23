<template>
  <div>
    <button @click="modal = !modal">modal</button>
    <v-modal title="제목" :modal="modal" @close="modal = false">
      <div slot="content">본문</div>
    </v-modal>
  </div>
</template>

<script>
import VModal from '@/components/VModal.vue';

export default {
  components: {
    'v-modal': VModal,
  },
  data() {
    return {
      modal: false,
    };
  },
};
</script>
