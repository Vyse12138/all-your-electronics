<template>
  <div>
    <h1>All Your Electronics</h1>
    <el-row>
      <el-col v-for="category in storeCatalog" :span="8">
        <el-card :body-style="{ padding: '0px' }">
          <router-link :to="'/category/' + category.name">
            <img
              :src="'http://localhost:3000/assets/' + category.img"
              class="image"
            />
          </router-link>
          <h2>{{ category.name }}</h2>
        </el-card>
      </el-col>
    </el-row>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const storeCatalog = [
  { name: 'phone', img: 'Phone.jpg' },
  { name: 'computer', img: 'Computer.jpg' },
  { name: 'TV', img: 'TV.jpg' },
  { name: 'camera', img: 'Camera.jpg' },
  { name: 'pad', img: 'Pad.jpg' },
  { name: 'headphone', img: 'Headphone.jpg' }
]
</script>

<style scoped>
.el-card {
  margin: 10px;
}
img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
</style>
