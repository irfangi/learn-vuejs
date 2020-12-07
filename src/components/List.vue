<template>
  <div v-on:click="method()">
    {{ test }}
  </div>
</template>

<script>
export default {
  props: { test: Number, method: { type: Function } },
};
</script>
