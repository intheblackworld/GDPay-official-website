<template>
  <div class="mx-auto">
    <img :src="src" class="xl:hidden w-[30vw] mt-[20px] mb-[40px] xl:mt-[40px] xl:mb-[80px] mx-auto xl:w-[300px] shadow-lg" alt="" @click="handleDialog" />
    <img :src="src" class="hidden xl:block w-[30vw] mt-[20px] mb-[40px] xl:mt-[40px] xl:mb-[80px] xl:w-[150px] xl:mx-0 mx-auto shadow-lg" alt="" />
    <Transition>
      <div v-if="isShowDialog" class="full-img fixed bg-black w-[100vw] h-[100vh] z-10 top-0 left-0 flex items-center content-center" @click="handleDialog">
        <img :src="src" alt="" class="w-[100%]">
      </div>
    </Transition>
  </div>
</template>
<script setup>
import { ref } from 'vue'
defineProps(['src'])

const isShowDialog = ref(false)
const handleDialog = () => {
  isShowDialog.value = !isShowDialog.value
}
</script>

<style scoped>
.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter,
.v-leave-to {
  opacity: 0;
}
</style>
