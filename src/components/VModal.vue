<template>
    <div class="modal-cover" v-show="modal" @click="$emit('close')">
        <div class="modal" @click.stop>
            <div class="modal-header">
                {{ title }}
            </div>
            <slot name="content"></slot>
        </div>
    </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
    },
    modal: {
      type: Boolean,
      default: false,
    },
  },
};
</script>

<style scoped>
    body {
        margin: 0;
        padding: 0;
    }

    .modal-cover {
        background: rgba(0, 0, 0, 0.5);
        width: 100%;
        position: absolute;
        height: 100%;
        z-index: 2;
        top: 0;
    }
    .modal {
        width: 400px;
        height: 400px;
        background: white;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        border: 1px solid grey;
        border-radius: 16px;
        box-shadow: 4px 4px 4px 4px #666;
        padding: 32px;
        z-index: 3;
    }
    .modal-header {
        font-size: 24px;
        font-weight: bold;
        border-bottom: 1px solid grey;
        margin-bottom: 8px;
        text-align: left;
    }
</style>
