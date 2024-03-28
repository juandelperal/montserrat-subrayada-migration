<script setup lang="ts">
import { ref } from 'vue'
const text = ref('jasd')
const useNew = ref(false)
const adjusted = ref(false)
const size = ref(2)
</script>

<template>
  <input type="range" v-model="size" step="0.01" min="0.7" max="3" />

  <p>
    <a href="#" @click.prevent="useNew = !useNew"> {{ useNew ? 'New' : 'Old' }} version</a>
    <a href="#" @click.prevent="adjusted = !adjusted">
      {{ adjusted ? 'Adjusted' : 'not adjusted' }}
    </a>
  </p>
  <div
    class="demo"
    :style="{ fontSize: size + 'em', fontFamily: useNew ? 'New' : 'Old' }"
    :class="{ adjusted: adjusted && useNew }"
    contenteditable="true"
    spellcheck="false"
  >
    <h1>Montserrat migration</h1>
    <p>
      Lorem, ipsum dolor sit amet consectetur adipisicing elit. Id, magni temporibus tempore aperiam
      aliquid commodi nostrum illo cumque odit libero omnis, aliquam beatae ab quae. Quo asperiores
      inventore repudiandae libero?
    </p>
  </div>
</template>

<style scoped>
.adjusted {
  text-transform: uppercase;
  font-weight: 600;
}
</style>
