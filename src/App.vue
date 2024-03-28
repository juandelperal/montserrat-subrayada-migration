<script setup lang="ts">
import { ref, onMounted } from 'vue'
const useNew = ref(false)
const adjusted = ref(false)
const size = ref(2)

onMounted(() => {
  setInterval(() => {
    useNew.value = !useNew.value
  }, 1000)
})
</script>

<template>
  <div class="code">
    <p>
      Include this in your css
      <span
        @click.prevent="adjusted = !adjusted"
        class="tag"
        :style="{ color: adjusted ? 'hsla(160, 100%, 37%, 1)' : 'red' }"
        >CORRECTION {{ adjusted ? 'ON' : 'OFF' }}</span
      >
    </p>
    <pre>
{
  text-transform: uppercase;
  font-weight: 600;
}</pre
    >
  </div>

  <p>
    <a class="mono" href="#" @click.prevent="useNew = !useNew">
      {{ useNew ? 'New' : 'Old' }} version</a
    >
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
.tag {
  cursor: pointer;
  padding: 0.2em 0.5em;
  border-radius: 0.2em;
}
.mono {
  font-family: monospace;
  text-transform: uppercase;
}
.code {
  font-family: monospace;
  background: whitesmoke;
  padding: 1em 2em;
}
pre {
  font-size: 2em;
}
.adjusted {
  text-transform: uppercase;
  font-weight: 600;
}
</style>
