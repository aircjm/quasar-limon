<template>
  <div>{{ name }}</div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'TaskLists',
  setup() {
    const name = ref('hello');
    return name;
  },
});
</script>
