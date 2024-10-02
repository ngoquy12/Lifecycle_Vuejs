<template>
  <div>
    <div v-if="isShow">
      <!-- <ChildrenComponent></ChildrenComponent> -->
      <Time :inputValue="inputValue" />
    </div>
    <h1>Parent Component</h1>
    <input type="text" v-model="inputValue" />

    <button @click="handleShow">Toggle</button>
  </div>
</template>

<script setup>
import ChildrenComponent from "./ChildrenComponent.vue";
import Time from "./Time.vue";
import { ref } from "vue";
const inputValue = ref("");

const isShow = ref(false);

const handleShow = () => {
  isShow.value = !isShow.value;
};
</script>
