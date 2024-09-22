<script setup>

</script>

<template>
  <div class="w-full h-screen m-auto mt-10 flex justify-center">
    
    <div class="relative">
      <img 
        src="../assets/images/pattern-bg.svg" 
        alt="Background image"
        class="absolute inset-0 w-[80%] mx-auto object-cover max-w-[450px]"
      >

      <img 
        src="../assets/images/image-tanya.jpg" 
        alt="Tanya"
        class="relative z-10 w-[64%] rounded object-cover mx-auto mt-6 sm:mt-8 shadow-photo lg:max-w-[1000px]"
      >

      <div class="relative w-20 left-1/2 transform -translate-x-1/2 lg:left-32 lg:translate-x-0 bottom-5 z-20 flex">
        <button class="bg-white w-full rounded-l-full p-3">
          <img src="../assets/images/icon-prev.svg" alt="Left arrow" class="w-3 h-3">
        </button>

        <button class="bg-white w-full rounded-r-full p-3">
          <img src="../assets/images/icon-next.svg" alt="Right arrow" class="w-3 h-3">
        </button>
      </div>
    </div>

    <img 
      src="../assets/images/pattern-curve.svg" 
      alt="Background image"
      class="absolute bottom-0 inset-x-0 w-full h-auto z-0 max-w-[600px]"
    >
  </div>
</template>

<style scoped>
.shadow-photo {
  box-shadow: 0 30px 30px -10px rgba(0, 0, 0, 0.2);
}
</style>
