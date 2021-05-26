<template>
  <v-dialog v-on="{ ...$listeners }" v-bind="{ ...$attrs }">
    <v-card :color="props.background">
      <h1>{{ props.title }}</h1>
      <slot name="someSlot"></slot>
    </v-card>
    <slot name="someOutSideSlot"></slot>
    <div class="d-flex justify-center">
      <v-btn class="mr-5" @click="confirm">Save</v-btn>
      <v-btn class="ml-5" @click="cancel">Cancel</v-btn>
    </div>
  </v-dialog>
</template>

<script lang='ts'>
import { defineComponent, ref } from '@vue/composition-api';

export default defineComponent({
  emits: ['confirm', 'cancel'],
  props: {
    title: {
      type: String,
      default: 'Default Title'
    },
    background: {
      type: String,
      default: '#8a1'
    }
  },
  data() {
    return { props: this.$props };
  },
  methods: {
    confirm() {
      this.$emit('confirm');
    },
    cancel() {
      this.$emit('cancel');
    }
  }
});
</script>
