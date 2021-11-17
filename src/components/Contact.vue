<template>
  <div>
    <button @click="isOpen = !isOpen"><img src="/assets/envelope-icon.svg" alt=""
        class=" w-10 h-10 text-lightColor"></button>


    <!-- modale -->
      <!-- blur -->
    <div v-if="isOpen === true"
      class=" z-10 blurPerso bg-lightColor absolute top-0 left-0 w-full h-full overflow-hidden"></div>


    <div v-if="isOpen === true"
      class=" z-20 bg-persoBlue w-2/3 h-20 absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2">
      <svg @click="isOpen = false" class="w-14 h-14" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
      </svg>
    </div>

  </div>
</template>

<script>
  export default {
    data() {
      return {
        isOpen: false,
      }
    },
  }
</script>