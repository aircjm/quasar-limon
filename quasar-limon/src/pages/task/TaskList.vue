<template>
<div>{{name}}</div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'TaskLists',
  setup() {
    const name = ref("hello")


  return name
  },
})
</script>

function ref(arg0: string) {
  throw new Error('Function not implemented.')
}
