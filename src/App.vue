<template>
  <Child ref="childRef"></Child>
  <button @click="outsideTrigger">Outside Trigger</button>
</template>

<script setup lang="ts">
import Child from '@/components/Child.vue';

import { ref, type ComponentInstance } from 'vue';
const childRef = ref<ComponentInstance<typeof Child>>();

function outsideTrigger() {
  childRef.value?.triggerAnimation()
}

</script>