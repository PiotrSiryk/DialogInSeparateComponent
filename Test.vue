<template>
  <div class="test">
    <UniversalDialog v-model="test"> </UniversalDialog>
    <v-btn @click="test = true">Open Dialog</v-btn>
  </div>
</template>

<script lang='ts'>
import UniversalDialog from '@/components/UniversalDialog.vue';

export default {
  data() {
    return { test: false };
  },

  components: { UniversalDialog }
};
</script>
