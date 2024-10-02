<template>
  <h1>Thời gian hiện tại: {{ time }}</h1>
</template>

<script setup>
import { onBeforeUnmount, onMounted, ref } from "vue";
let timerId;

const formatDate = (date) => {
  const today = new Date(date);

  // Lấy ra giờ
  const hours = today.getHours().toString().padStart(2, 0);

  // Lấy ra phút
  const minutes = today.getMinutes().toString().padStart(2, 0);

  // Lấy ra giây
  const seconds = today.getSeconds().toString().padStart(2, 0);

  return `${hours} : ${minutes} : ${seconds}`;
};

const time = ref(formatDate(new Date()));

onMounted(() => {
  timerId = setInterval(() => {
    time.value = formatDate(new Date());
  }, 1000);
});

onBeforeUnmount(() => {
  clearInterval(timerId);
});
</script>
