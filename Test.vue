  
<template>
  <div class="test">
    <div>
      <UniversalDialog
        v-model="dogs"
        title="dogs"
        @cancel="closePopup"
        @confirm="doStuff"
        background="red"
      >
        <template #someSlot>
          <div>doooooooooooooogs</div>
        </template>
        <template #someOutSideSlot>
          <div>dogs but outside</div>
        </template>
      </UniversalDialog>
      <v-btn @click="dogs = true">Open dogs</v-btn>
    </div>
    <div>
      <UniversalDialog
        v-model="cats"
        title="cats"
        @confirm="doStuff"
        @cancel="closePopup"
        background="green"
      >
        <template #someOutSideSlot>
          <div>caaaaaaaaats but outside</div>
        </template>
      </UniversalDialog>
      <v-btn @click="cats = true">Open cats</v-btn>
    </div>
    <div>
      <UniversalDialog
        v-model="drugs"
        title="drugs"
        background="blue"
        @confirm="doStuff"
        @cancel="closePopup"
      >
        <template #someSlot>
          <div>druuuuuuugs but outside</div>
        </template>
      </UniversalDialog>
      <v-btn @click="drugs = true">Open drugs</v-btn>
    </div>
  </div>
</template>

<script lang='ts'>
import UniversalDialog from '@/components/UniversalDialog.vue';
export default {
  data() {
    return { dogs: false, cats: false, drugs: false };
  },
  methods: {
    doStuff() {
      console.log('stuff');
    },
    closePopup() {
      this.dogs = false;
      this.cats = false;
      this.drugs = false;
    }
  },
  components: { UniversalDialog }
};
</script>
