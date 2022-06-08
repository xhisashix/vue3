<script setup>
import { ref } from "vue";

const number = ref(0);

const add = () => {
  number.value++;
};
</script>

<template>
  <div>
    <input type="text" size="30" v-model="number" />
    <button @click="add()">ボタン</button>
  </div>
</template>
