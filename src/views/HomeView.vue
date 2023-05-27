<script setup lang="ts">
import { ref } from 'vue';
import CButton from '../components/CButton.vue';
import { CButtonShapes, Sizes } from '../types';

const sizes: Sizes[] = ['sm', 'md', 'lg'];
const size = ref<Sizes>('sm');

const shapes: CButtonShapes[] = ['default', 'rounded'];
const shape = ref<CButtonShapes>('default');

const loading = ref(false);
</script>

<template>
  <main>
    <c-button label="Test" :size="size" :shape="shape" :loading="loading" />

    <template v-for="sizeVal in sizes" :key="sizeVal">
      <label :for="sizeVal">{{ sizeVal }}</label>
      <input v-model="size" type="radio" name="size" :value="sizeVal" />
    </template>

    <template v-for="val in shapes" :key="val">
      <label :for="val">{{ val }}</label>
      <input v-model="shape" type="radio" name="shape" :value="val" />
    </template>

    <label for="loading">Loading</label>
    <input v-model="loading" type="checkbox" name="loading" />
  </main>
</template>
