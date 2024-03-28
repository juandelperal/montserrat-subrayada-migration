<script setup lang="ts">
import { ref } from 'vue'
const text = ref('jasd')
const useNew = ref(true)
const size = ref(15)
</script>

<template>
  <input type="range" v-model="size" />
  <p>
    <a href="#" @click.prevent="useNew = !useNew"> {{ useNew ? 'New' : 'Old' }} Montserrat</a>
  </p>
  <h1>Montserrat</h1>
  <p :style="{ fontSize: size + 'px' }">
    Lorem, ipsum dolor sit amet consectetur adipisicing elit. Id, magni temporibus tempore aperiam
    aliquid commodi nostrum illo cumque odit libero omnis, aliquam beatae ab quae. Quo asperiores
    inventore repudiandae libero?
  </p>
</template>

<style scoped></style>
