<template>
  <div>
    <button @click="showModal">模态框</button>
    <div v-if="isModalVisible" class="modal-container" @click="hideModal">
      <div class="modal" @click.stop>
        <div class="modal-header">
          <slot name="header">
            <h1>标题</h1>
          </slot>
          <span @click="hideModal" class="close-button">X</span>
        </div>
        <div class="modal-body">
          <slot name="content">
            <input type="text" placeholder="默认内容">
          </slot>
        </div>
        <div class="modal-footer">
          <slot name="footer">
            <span>底部</span>
          </slot>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isModalVisible: false,
    };
  },
  methods: {
    showModal() {
      this.isModalVisible = true;
    },
    hideModal() {
      this.isModalVisible = false;
    },
  },
};
</script>

<style scoped>
.modal-container {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal {
  width: 300px;
  height: 200px;
  background-color: white;
  border-radius: 10px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
  padding: 20px;
  max-width: 400px;
}

.modal-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.close-button {
  cursor: pointer;
}

.modal-body {
  margin-top: 10px;
}

.modal-footer {
  margin-top: 10px;
  text-align: right;
}
</style>
  