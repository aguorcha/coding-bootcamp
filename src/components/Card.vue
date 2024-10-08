<script setup>
import { ref, computed } from 'vue';

const testimonials = ref([
{
    image: 'https://i.postimg.cc/qv4MqRTp/image-tanya.jpg',
    testimonial: "I’ve been interested in coding for a while but never taken the jump, until now. I couldn’t recommend this course enough. I’m now in the job of my dreams and so excited about the future.",
    name: 'Tanya Sinclair',
    role: 'UX Engineer',
  },
  {
    image: 'https://i.postimg.cc/503mcjbj/image-john.jpg',
    testimonial: "If you want to lay the best foundation possible I’d recommend taking this course. The depth the instructors go into is incredible. I now feel so confident about starting up as a professional developer.",
    name: 'John Tarkpor',
    role: 'Junior Front-end Developer',
  }
]);

const currentIndex = ref(0);

const goToPrev = () => {
  currentIndex.value = (currentIndex.value - 1 + testimonials.value.length) % testimonials.value.length;
};

const gotToNext = () => {
  currentIndex.value = (currentIndex.value + 1) % testimonials.value.length;
}

const currentTestimonial = computed(() => testimonials.value[currentIndex.value]);
</script>

<template>
  <div class="w-full h-screen m-auto mt-10 lg:-mt-4 flex flex-col items-center lg:flex-row-reverse lg:w-[90%]">
    
    <div class="relative lg:w-1/2">
      <img 
        src="../assets/images/pattern-bg.svg" 
        alt="Background image"
        class="absolute inset-0 w-[80%] mx-auto object-cover max-w-[600px]"
      >

      <img 
        :src="currentTestimonial.image" 
        alt="Current testimonial"
        class="relative z-10 w-[64%] sm:w-[62%] rounded object-cover mx-auto mt-6 sm:mt-10 shadow-photo lg:w-[64%]"
      >

      <div class="relative w-20 left-1/2 transform -translate-x-1/2 lg:left-52 lg:translate-x-0 bottom-5 z-20 flex">
        <button @click="goToPrev" class="bg-white w-full rounded-l-full p-3">
          <img src="../assets/images/icon-prev.svg" alt="Left arrow" class="w-3 h-3">
        </button>

        <button @click="gotToNext" class="bg-white w-full rounded-r-full p-3">
          <img src="../assets/images/icon-next.svg" alt="Right arrow" class="w-3 h-3">
        </button>
      </div>
    </div>

    <div class="lg:relative w-[80%] flex flex-col items-center mt-6 text-center z-10 lg:items-start lg:text-left  lg:w-1/2">
      <img 
        src="../assets/images/pattern-quotes.svg" 
        alt="Background image"
        class="relative w-14 lg:w-20 lg:left-44 lg:-top-16"
      >
      <p class="w-full -mt-6 font-light lg:absolute lg:left-32 lg:text-xl">{{ currentTestimonial.testimonial }}</p>
      <div class="mt-4 lg:flex lg:ml-32 lg:mt-10">
        <h2 class="font-bold">{{ currentTestimonial.name }}</h2>
        <span class="text-grayish-blue lg:ml-2">{{ currentTestimonial.role }}</span>
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
