<template>
  <startButton @click="showPopup" />
  <submitForm v-if="isVisible" />
</template>

<script>
import startButton from "@/components/startButton";
import submitForm from "@/components/submitForm.vue";
export default {
  components: { startButton, submitForm },
  data() {
    return {
      isVisible: false,
    };
  },
  methods: {
    showPopup() {
      this.isVisible = !this.isVisible;
    },
  },
};
</script>
