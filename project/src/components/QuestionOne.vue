<template>
  <div>
    <input v-model="inputText" @keyup.enter="addItem" placeholder="请输入内容" />
    <button @click="addItem">添加</button>
    <ul>
      <li v-for="(item, index) in itemList" :key="index">{{ item }}</li>
    </ul>
  </div>
</template>
  
<script>
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'QuestionOne',
    data() {
      return {
        inputText: '',
        itemList: []
      };
    },
    methods: {
      addItem() {
        if (this.inputText.trim() !== '') {
          this.itemList.push(this.inputText);
          this.inputText = '';
        }
      }
    }
})
</script>

<style scoped>
  ul li {
    list-style: none;
    border: 1px solid #000;
    border-radius: 10px;
    padding: 5px 10px;
    margin: 10px auto;
  }
</style>