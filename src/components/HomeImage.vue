<template>
  <div class=" relative w-1/2 cursor-pointer " >
        <!-- img mobile -->
        <img @click="displayText = !displayText, ping = false" :src="`https://res.cloudinary.com/sarah3902/image/upload/q_auto/fl_lossy/ar_1:1,c_fill,g_north${HomeDatas.mainImage}`" alt="Sarah LEROY" class=" lg:hidden w-full rounded-md transition-all shadow-xl" :class="{'blurPerso':displayText}">
        <!-- img desktop -->
        <img :src="`https://res.cloudinary.com/sarah3902/image/upload/q_auto/fl_lossy/ar_5:3,c_fill,g_face${HomeDatas.mainImage}`" alt="Sarah LEROY" class=" hidden lg:block w-full rounded-md transition-all shadow-xl cursor-auto">
        <div v-show="ping" @click="displayText = !displayText, ping = false" class="lg:hidden absolute -top-1 -right-1 w-5 h-5 bg-persoBlue rounded-full animate-ping"></div>
        <div v-show="displayText" @click="displayText = !displayText" class=" lg:hidden absolute top-0 left-0 flex justify-center items-center w-full h-full">
          <h2 class=" text-lightColor text-[12px] p-2 transition-all">{{HomeDatas.description}}</h2>
        </div>

        <h2 class=" hidden lg:block text-lightColor text-center text-sm p-2 transition-all">{{HomeDatas.description}}</h2>
        <img :src="`https://res.cloudinary.com/sarah3902/image/upload/q_auto/fl_lossy${HomeDatas.logo_black}`" alt="" class=" hidden lg:block w-full rounded-md transition-all shadow-xl cursor-auto">
  </div>
</template>

<script>
import HomeDatas from "../pagesDatas/home.json"
  export default {
    data() {
      return {
        HomeDatas,
        displayText: false,
        ping: true,
      }
    },
  }
</script>

<style>
  .blurPerso {
    filter: blur(10px) drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.25));
  }
  .shadowPerso {
    filter: drop-shadow(0px 4px 10px rgba(0, 0, 0, 0.25));
  }
</style>