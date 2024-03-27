<template>
  <div v-for="input in inputValue">{{ input.name }}: {{ input.value }}</div>
</template>

<script>
export default {
  props: {
    inputValue: {
      type: Object,
    },
  },
};
</script>
