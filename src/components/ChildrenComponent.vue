<template>
  <h1>Children component</h1>
  <input type="text" v-model="inputValue" />
  <h2>Count: {{ count }}</h2>
  <button @click="handleCount">Count</button>
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

const count = ref(0);
const inputValue = ref("");

const handleCount = () => {
  count.value++;
};

// Các phương thức trong giai đoạn Mounting
onBeforeMount(() => {
  //   count.value = 5;
  console.log("Component before mount");
});

onMounted(() => {
  //   count.value = 6;
  console.log("Component mounted");
});

// Các phương thức trong giai đoạn updation
onBeforeUpdate(() => {
  document.title = inputValue.value;
  console.log("Before update");
});

onUpdated(() => {
  inputValue.value = "Nguyễn Văn A";
  console.log("Component Updated");
});

// Các phương thức trong giai đoạn unmount
onBeforeUnmount(() => {
  console.log("Component before unmount");
});

onUnmounted(() => {
  console.log("Component mounted");
});
</script>

<style></style>
