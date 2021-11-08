<template>
  <div class=" relative w-1/2 cursor-pointer ml-4 mt-9 mb-16" >
        <img @click="displayText = !displayText" :src="`https://res.cloudinary.com/sarah3902/image/upload/f_auto/q_auto/c_scale/fl_lossy/ar_1:1,c_fill,g_north${HomeDatas.mainImage}`" alt="Sarah LEROY" class=" w-full rounded-md transition-all" :class="{'blurPerso':displayText}">
        <div @click="displayText = !displayText" class=" absolute top-[-0.4rem] right-[-0.4rem] w-6 h-6 bg-persoBlue shadow-md rounded-full blur-sm"></div>
        <div @click="displayText = !displayText" class=" absolute -top-1 -right-1 w-5 h-5 bg-persoBlue shadow-md rounded-full"></div>
        <div v-show="displayText" @click="displayText = !displayText" class=" absolute top-0 left-0 flex justify-center items-center w-full h-full">
          <h2 class=" text-lightColor text-center text-sm p-2 transition-all">{{HomeDatas.description}}</h2>
        </div>
  </div>
</template>

<script>
import HomeDatas from "../pagesDatas/home.json"
  export default {
    data() {
      return {
        HomeDatas,
        displayText: false,
      }
    },
  }
</script>

<style>
  .blurPerso {
    filter: blur(10px) drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.25));
  }
</style>