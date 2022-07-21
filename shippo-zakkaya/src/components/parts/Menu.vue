<template>
  <div
    class="menu-button bg-primary"
    @click="isOpen = !isOpen"
  >
    <div class="humberger" :class="{ active: isOpen }">
      <span :class="{ active: isOpen }"></span>
      <span :class="{ active: isOpen }"></span>
      <span :class="{ active: isOpen }"></span>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";

const isOpen = ref(false);
</script>

<style lang="scss">
$button-size: 50px;
.menu-button {
  width: $button-size;
  height: $button-size;
  border-radius: 5px;
}
.humberger {
  position: relative;
  span {
    transition: all 0.4s;
    position: absolute;
    left: calc($button-size/4);

    background-color: #fff;
    height: 2px;
    width: 50%;
    border-radius: 5px;
    &:nth-of-type(1) {
      top: 13px;
      &.active {
        top: 14px;
        left: calc($button-size/4 + 4px);
        transform: translateY(6px) rotate(-45deg);
        width: 30%;
      }
    }
    &:nth-of-type(2) {
      top: 19px;
      &.active {
        opacity: 0;
      }
    }
    &:nth-of-type(3) {
      top: 25px;
      &.active {
        top: 26px;
        left: calc($button-size/4 + 4px);
        transform: translateY(-6px) rotate(45deg);
        width: 30%;
        &::after {
          content: "Close";
          transform: translateY(0) translate(3px) rotate(-45deg);
        }
      }
      &::after {
        content: "Menu";
        position: absolute;
        top: 5px;
        left: -3px;
        color: #fff;
        text-transform: uppercase;
        font-size: 0.6rem;
      }
    }
  }
}
</style>
