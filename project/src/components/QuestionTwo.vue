<template>
  <div>
    <input v-model="keyword" placeholder="请输入关键字" @input="filterData" />
    <table>
      <thead>
        <tr>
          <th>序号</th>
          <th>姓名</th>
          <th>年龄</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="item in filteredData" :key="item.id">
          <td>{{ item.id }}</td>
          <td>{{ item.name }}</td>
          <td>{{ item.age }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      keyword: '',
      data: [
        { id: 1, name: 'Join', age: 25 },
        { id: 2, name: 'Alone', age: 18 },
        { id: 3, name: 'gegi', age: 20 },
      ],
    };
  },
  computed: {
    filteredData() {
      // 根据关键字筛选数据
      const keyword = this.keyword.toLowerCase();
      return this.data.filter(item =>
        item.name.toLowerCase().includes(keyword) ||
        String(item.age).includes(keyword)
      );
    },
  },
  methods: {
    filterData() {
      // 当输入框内容改变时触发筛选
      this.filteredData;
    },
  },
};
</script>

<style lang="scss" scoped>
  table {
    border: 1px solid #000;
  }
</style>