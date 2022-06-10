<template>
  <div>
    <h1 ref="title">タイトル</h1>
    <p>タスクを追加</p>
    <p>{{ newTodo }}</p>
    <input type="text" name="todo" v-model="newTodo" />
    <button @click="addTodo">追加</button>
    <ul>
      <li v-for="todo in array" :key="todo.index">{{ todo }}</li>
    </ul>
    <p>あなたの点数は何点ですか？</p>
    <input type="number" v-model="score" />
    <button @click="judge">結果を表示</button>
    <p v-if="boolean">合格です。</p>
    <p v-else-if="boolean == null"></p>
    <p v-else>不合格です。</p>
  </div>
</template>

<script>
import { ref } from "vue";
export default {
  setup() {
    const title = ref();
    const array = ref([]);
    const newTodo = ref();
    const boolean = ref();
    const score = ref();

    const addTodo = () => {
      array.value.push(newTodo.value);
    };

    const judge = () => {
      if (score.value < 50) {
        boolean.value = false;
      } else {
        boolean.value = true;
      }
    };

    return {
      title,
      array,
      newTodo,
      addTodo,
      score,
      boolean,
      judge,
    };
  },
};
</script>

<style lang="css"></style>
