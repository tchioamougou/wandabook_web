<template>
  <div class="carousel bg-gray-500 relative container " style="">
    <div class="carousel-inner relative overflow-hidden w-full">
      <!--Slide 1-->
      <input class="carousel-open" type="radio" id="carousel-1" name="carousel" aria-hidden="true" hidden=""
        checked="checked">
      <div class="carousel-item absolute opacity-0" style="height:60vh;">
        <div class=" h-full w-full mx-auto flex pt-6 md:pt-0 md:items-center bg-cover bg-right"
          style="background-image: url(https://templates-demo.in/prestashop/naomi/modules/df_mainslider/views/img/sample-1.jpg)">
          <div class="container mx-auto"> </div>
        </div>
      </div>

      <label for="carousel-3"
        class="prev control-1 w-10 h-10 ml-2 md:ml-10 absolute cursor-pointer hidden text-3xl font-bold text-black hover:text-white rounded-full bg-opacity-20 bg-white hover:bg-gray-900 leading-tight text-center z-10 inset-y-0 left-0 my-auto">‹</label>
      <label for="carousel-2"
        class="next control-1 w-10 h-10 mr-2 md:mr-10 absolute cursor-pointer hidden text-3xl font-bold text-black hover:text-white rounded-full bg-opacity-20 bg-white hover:bg-gray-900 leading-tight text-center z-10 inset-y-0 right-0 my-auto">›</label>

      <!--Slide 2-->
      <input class="carousel-open" type="radio" id="carousel-2" name="carousel" aria-hidden="true" hidden="">
      <div class="carousel-item absolute opacity-0 bg-cover bg-right" style="height:60vh;">
        <div class="block h-full w-full mx-auto flex pt-6 md:pt-0 md:items-center bg-cover bg-right"
          style="background-image: url(https://templates-demo.in/prestashop/naomi/modules/df_mainslider/views/img/sample-3.jpg)">

        </div>
      </div>
      <label for="carousel-1"
        class="prev control-2 w-10 h-10 ml-2 md:ml-10 absolute cursor-pointer hidden text-3xl font-bold text-black hover:text-white rounded-full bg-opacity-20 bg-white hover:bg-gray-900  leading-tight text-center z-10 inset-y-0 left-0 my-auto">‹</label>
      <label for="carousel-3"
        class="next control-2 w-10 h-10 mr-2 md:mr-10 absolute cursor-pointer hidden text-3xl font-bold text-black hover:text-white rounded-full bg-opacity-20 bg-white hover:bg-gray-900  leading-tight text-center z-10 inset-y-0 right-0 my-auto">›</label>

      <!--Slide 3-->
      <input class="carousel-open" type="radio" id="carousel-3" name="carousel" aria-hidden="true" hidden="">
      <div class="carousel-item absolute opacity-0" style="height:60vh;">
        <div class="block h-full w-full mx-auto flex pt-6 md:pt-0 md:items-center bg-cover bg-center"
          style="background-image: url('https://images.unsplash.com/photo-1603584173870-7f23fdae1b7a?crop=entropy&cs=srgb&fm=jpg&ixid=MnwxNDU4OXwwfDF8cmFuZG9tfHx8fHx8fHx8MTYzMzcwMDk1NA&ixlib=rb-1.2.1&q=85;">
        </div>
      </div>
      <label for="carousel-2"
        class="prev control-3 w-10 h-10 ml-2 md:ml-10 absolute cursor-pointer hidden text-3xl font-bold text-black hover:text-white rounded-full bg-opacity-20 bg-white hover:bg-red-600 leading-tight text-center z-10 inset-y-0 left-0 my-auto">‹</label>
      <label for="carousel-1"
        class="next control-3 w-10 h-10 mr-2 md:mr-10 absolute cursor-pointer hidden text-3xl font-bold text-black hover:text-white rounded-full bg-opacity-20 bg-white hover:bg-red-600  leading-tight text-center z-10 inset-y-0 right-0 my-auto">›</label>

      <!-- slide indicators -->
      <ol class="carousel-indicators">
        <li class="inline-block mr-3">
          <label for="carousel-1"
            class="carousel-bullet cursor-pointer block text-4xl text-gray-400 hover:text-gray-900">•</label>
        </li>
        <li class="inline-block mr-3">
          <label for="carousel-2"
            class="carousel-bullet cursor-pointer block text-4xl text-gray-400 hover:text-gray-900">•</label>
        </li>
        <li class="inline-block mr-3">
          <label for="carousel-3"
            class="carousel-bullet cursor-pointer block text-4xl text-gray-400 hover:text-gray-900">•</label>
        </li>
      </ol>

    </div>
  </div>

</template>

<script setup>
import { ref, onMounted } from 'vue';
import lecture7 from "../assets/images/lecture7.gif"
import lecture3 from "../assets/images/lecture3.gif"
import lecture6 from "../assets/images/lecture6.gif"



const currentIndex = ref(0);
const items = ref([
  { image: lecture7, alt: 'Image 1' },
  { image: lecture3, alt: 'Image 2' },
  { image: lecture6, alt: 'Image 3' },
]);

const next = () => {
  currentIndex.value = (currentIndex.value + 1) % items.value.length;
};

const prev = () => {
  currentIndex.value = (currentIndex.value - 1 + items.value.length) % items.value.length;
};

const autoSlide = () => {
  setInterval(next, 8000); // Change d'image toutes les 3 secondes
};

onMounted(() => {
  autoSlide();
});
</script>

<style scoped>
.carousel-open:checked+.carousel-item {
  position: static;
  opacity: 100;
}

.carousel-item {
  -webkit-transition: opacity 0.4s ease-in-out;
  transition: opacity 0.4s ease-in-out;
}

#carousel-1:checked~.control-1,
#carousel-2:checked~.control-2,
#carousel-3:checked~.control-3 {
  display: block;
}

.carousel-indicators {
  list-style: none;
  margin: 0;
  padding: 0;
  position: absolute;
  bottom: 2%;
  left: 0;
  right: 0;
  text-align: center;
  z-index: 10;
}

#carousel-1:checked~.control-1~.carousel-indicators li:nth-child(1) .carousel-bullet,
#carousel-2:checked~.control-2~.carousel-indicators li:nth-child(2) .carousel-bullet,
#carousel-3:checked~.control-3~.carousel-indicators li:nth-child(3) .carousel-bullet {
  color: #000;
  /*Set to match the Tailwind colour you want the active one to be */
}
</style>