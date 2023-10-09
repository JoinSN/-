<template>
  <div class="carousel">
    <div class="slide">
      <img :src="images[currentIndex].url" alt="图像无法显示，请连接网络！" />
    </div>
    <div class="pagination">
      <span
        v-for="(item, index) in images" :key="item.id"
        @click="currentIndex = index"
        :class="{ active: index === currentIndex }"
      ></span>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentIndex: 0,
      images: [
        {id: 1, url: 'https://cdn.pixabay.com/photo/2020/07/12/16/49/poppy-5397906_1280.jpg'},
        {id: 2, url: 'https://cdn.pixabay.com/photo/2022/09/29/10/46/grass-7487114_1280.jpg'},
        {id: 3, url: 'https://cdn.pixabay.com/photo/2023/06/23/19/34/campfire-8084064_1280.jpg'},
      ],
    };
  },
  mounted() {
    setInterval(() => {
      this.currentIndex = (this.currentIndex + 1) % this.images.length;
    }, 2000);
  },
};
</script>

<style>
.carousel {
  position: relative;
  width: 100%;
  max-width: 600px;
}

.slide {
  position: relative;
  width: 100%;
  overflow: hidden;
}

img {
  width: 100%;
  height: auto;
}

.pagination {
  display: flex;
  justify-content: center;
  margin-top: 10px;
}

.pagination span {
  width: 10px;
  height: 10px;
  margin: 0 5px;
  background-color: #888;
  border-radius: 50%;
  cursor: pointer;
}

.pagination span.active {
  background-color: #333;
}
</style>
