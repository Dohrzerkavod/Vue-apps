<template>
  <div id="app" class="flex items-center justify-center min-h-screen p-4">
    <div class="text-center max-w-screen-md">
      <div class="mb-4">
        <input
          v-model="inputText"
          type="text"
          placeholder="Enter text"
          class="border p-2 w-full"
        />
      </div>
      <div class="mt-12">
        <FontSizeText :text="inputText" />
      </div>
    </div>
  </div>
</template>

<script>
import FontSizeText from './components/FontSizeText.vue';

export default {
  name: 'App',
  components: {
    FontSizeText
  },
  data() {
    return {
      inputText: ''
    };
  }
};
</script>

<style>
/* Optional global styles */
</style>
