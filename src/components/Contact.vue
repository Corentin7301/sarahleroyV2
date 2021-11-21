<template>
  <div>
    <button @click="isOpen = !isOpen"><svg class="w-11 h-11 text-lightColor" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"></path></svg></button>


    <!-- modale -->
    <!-- blur -->
    <div v-if="isOpen" @click="isOpen = !isOpen"
      class=" z-10 blurPerso transition-all absolute top-0 left-0 w-full h-full overflow-hidden"></div>
    <div v-if="isOpen"
      class=" z-20 bg-persoBlue w-[85%] absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 rounded-md py-5 px-6 transition-all">
      <svg @click="isOpen = false" class="absolute top-1 right-1 w-10 h-10 text-lightColor " fill="none"
        stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
      </svg>
      <p class=" text-lightColor text-center">Contact</p>
      <form action="" class=" space-y-3 mt-5 flex flex-col justify-center items-center">
        <input type="text" name="name" id="name" placeholder="Nom et prénom">
        <input type="email" name="email" id="email" placeholder="Email">
        <textarea name="message" id="message" cols="30" rows="10" placeholder="Message"></textarea>
        <input type="submit" value="Envoyer">
      </form>
      <div class="space-y-2 mt-2">
        <div class="flex items-center space-x-3">
          <svg class="w-6 h-6 text-lightColor" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"></path></svg>
          <a :href="`tel:${informationsDatas.phone.phoneUrl}`"
            class=" text-lightColor">{{informationsDatas.phone.phoneLabel}}</a>
        </div>
        <div class="flex items-center space-x-3">
          <svg class="w-6 h-6 text-lightColor" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"></path></svg>
          <a :href="`mailto:${informationsDatas.email}`" class=" text-lightColor">{{informationsDatas.email}}</a>
        </div>
      </div>
    </div>

  </div>
</template>

<script>
  import informationsDatas from "../datas/informationDatas.json";
  export default {
    data() {
      return {
        isOpen: false,
        informationsDatas,
      }
    },
  }
</script>

<style scoped lang="scss">
  input,
  textarea {
    @apply w-full block rounded-md py-1 px-2 m-auto;
  }

  input::placeholder,
  textarea::placeholder {
    color: rgba(0, 0, 0, 0.45);
  }

  input[type=submit] {
    @apply w-32 m-0 self-end;
    color: rgba(0, 0, 0, 0.45);

    &:hover {
      @apply text-lightColor bg-persoBlue border-2 border-lightColor box-border transition-all;
    }
  }
</style>