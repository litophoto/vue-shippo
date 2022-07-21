<template>
  <!-- <img :src="getImageUrl(assetsImage)" alt=""> -->
  <div class="row">
    <div class="col-sm-4">
      <img :src="getImageUrl(imageList[loopCounter-1])" alt="" class="img-fluid">
    </div>
    <div class="col-sm-4">
      <img :src="getImageUrl(imageList[loopCounter])" alt="" class="img-fluid">
    </div>
    <div class="col-sm-4">
      <img :src="getImageUrl(imageList[loopCounter + 1])" alt="" class="img-fluid">
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
const getImageUrl = (photoName) => {
  return new URL(`../../assets/image/${photoName}`, import.meta.url).href
}
const assetsImage = "ec-site-sample2.jpeg"
const imageList = [
  "main01.jpeg",
  "main02.jpeg",
  "main03.jpeg",
  "main05.jpeg",
]
const loopCounter = ref(0)
</script>

<style lang="scss">
  
</style>