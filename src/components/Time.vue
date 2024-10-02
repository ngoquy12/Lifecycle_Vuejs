<template>
  <h1>Time: {{ time }}</h1>
  <h2>InputValue: {{ props.inputValue }}</h2>
</template>

<script setup>
import {
  onBeforeMount,
  onBeforeUnmount,
  onBeforeUpdate,
  onMounted,
  onUnmounted,
  onUpdated,
  ref,
} from "vue";

const time = ref(0);
let timerId;

const props = defineProps({
  inputValue: {
    type: String,
    default: "Nguyễn Văn A",
  },
});

// Giai đoạn mouting
onBeforeMount(() => {
  console.log("Component before mount");
});

onMounted(() => {
  // timerId = setInterval(() => {
  //   time.value++;
  // }, 1000);
  console.log("Component mounted");
});

// Giai đoạn updating
onBeforeUpdate(() => {
  console.log("Component before update");
});

onUpdated(() => {
  console.log("Component updated");
});

// Giai đoạn unmount
onBeforeUnmount(() => {
  console.log("Component before unmount");
  clearInterval(timerId);
});

onUnmounted(() => {
  console.log("Component unmounted");
});
</script>

<style></style>
