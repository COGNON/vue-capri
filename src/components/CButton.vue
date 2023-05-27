<template>
  <button
    :class="[
      sizeCls,
      shapeCls,
      'bg-neutral-700',
      'hover:bg-neutral-600',
      'shadow-md',
      'font-medium',
      'uppercase',
      'p-1',
    ]"
  >
    <template v-if="loading">
      <c-loader />
    </template>
    <template v-else>
      {{ label }}
    </template>
  </button>
</template>

<script setup lang="ts">
import { computed } from 'vue';
import { CButtonShapes, Sizes } from '../types';
import CLoader from './CLoader.vue';

type Props = {
  label?: string;
  size?: Sizes;
  shape?: CButtonShapes;
  loading?: boolean;
};

const props = withDefaults(defineProps<Props>(), {
  label: '',
  size: 'md',
  shape: 'default',
  loading: false,
});

const sizeCls = computed(() => {
  if (props.size === 'sm') return 'w-[48px] h-[30px]';
  if (props.size === 'lg') return 'w-[88px] h-[55px]';
  return ' w-[78px] h-[38px]';
});

const shapeCls = computed(() => {
  if (props.shape === 'rounded') return 'rounded-full';
  return 'rounded-lg';
});
</script>
