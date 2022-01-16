<template>
  <div class="container block w-screen">
    <!-- Header -->
    <div class="header w-screen h-screen relative bg-gray-900">
      <div class="absolute z-50 ">
        <div class="flex items-end justify-end w-screen h-screen pb-10 pr-10 md:pb-20 md:pr-20">
          <!-- Portfolio -->
          <div class="title">
            <h1 class="text-5xl md:text-7xl font-extrabold text-white">
              <span class="text-6xl  md:text-8xl text-transparent bg-clip-text bg-gradient-to-tr from-yellow-600 to-yellow-500">PORT</span><span>FOLIO</span>
            </h1>
            <h2 class="text-xl md:text-4xl font-extrabold text-white">Nattapon Wongsuwan</h2>
            <p class="text-sm md:text-base font-extrabold text-white">AGE : {{ new Date().getFullYear() - birthday_year }} YEARS OLD</p>
            <router-link :to="{ path: '/contact' }">
              <button class="flex sm:inline-flex justify-center tems-center bg-gradient-to-tr from-yellow-600 to-yellow-400 hover:from-yellow-600  hover:to-yellow-500  active:from-yellow-700 active:to-yellow-600 focus-visible:ring ring-yellow-300 text-white font-semibold text-center rounded-lg outline-none transition duration-100 px-5 py-2 my-4">Contact</button>
            </router-link>
          </div>
        </div>
      </div>
      <!-- img BG -->
      <div class="w-screen h-screen ">
        <img class="w-full h-full object-cover opacity-10"
          src="https://images.unsplash.com/photo-1571171637578-41bc2dd41cd2?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1740&q=80"
          alt=""/>
      </div>
    </div>

    <!-- Education -->
    <div class="Education w-screen p-10 bg-gradient-to-r from-gray-100 to-gray-300">
      <!-- Title Education -->
      <div class="flex justify-center md:mx-40 md:mb-20 mb-10 items-end ">
        <div class="h-0.5 w-32 bg-yellow-400 mb-1"></div>
        <div class="txt flex justify-center items-center">
          <h1 class="text-center text-3xl md:text-5xl font-extrabold stloke">EDUCATION <br/><span class="txt-stroke font-black">BACKGROUND</span> 
          </h1>
        </div>
        <div class="h-0.5 w-32 bg-yellow-400 mb-1"></div>
      </div>
      
      <!-- Data -->
      <div class="row">
        <div v-for="edu in educations" :key="edu.id">
          <div class="py-6 md:px-40 h-40">
            <div class="flex ">
              <div class="block h-4 w-4 rounded-full mt-2 mr-3 bg-gradient-to-tr from-yellow-600 to-yellow-500"></div>
              <span >
                <h1 class="text-xl md:text-2xl font-extrabold">{{ edu.name }}</h1>
                <p class="text-base md:text-xl font-medium text-gray-500">{{ edu.program }}</p>
              </span>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Skills -->
    <div class="Skills w-screen p-10 my-6">
      <!-- Title Skill -->
      <div class="flex justify-center md:mx-40 md:mb-20 mb-10 items-end ">
        <div class="h-0.5 w-12 md:w-32 bg-yellow-400 mb-1"></div>
        <div class="txt  ">
          <h1 class="text-center text-3xl md:text-5xl font-extrabold">SKILL<span class="txt-stroke font-black">S</span></h1>
        </div>
        <div class="h-0.5 w-12 md:w-32 bg-yellow-400 mb-1"></div>
      </div>
      <!-- Skill Bar -->
      <div class="row md:px-40">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-4 ">
          <div class="py-1 md:py-2 " v-for="sk in skills" :key="sk.id">
            <h1 class="text-xl font-bold m-1">{{ sk.planguage }}</h1>
              <div class="w-full bg-gray-200 rounded-md h-5 md:h-7 shadow-inner">
                <div
                  class="flex sm:inline-flexjustify-center items-center  bg-gradient-to-tr from-yellow-600 to-yellow-500 h-5 md:h-7 rounded-md":style="{width: sk.score}">
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <Footer></Footer>
</template>

<script>
import Footer from '../components/pfooter.vue';
export default {
  name: 'profile',
  components: {
    Footer: Footer,
  },
  data() {
    return {
      birthday_year: 2000,
      age: 5,
      skills: [
        { id: 1, planguage: 'Xamarin', score: '75%' },
        { id: 2, planguage: 'C#', score: '75%' },
        { id: 3, planguage: 'JAVA', score: '50%' },
        { id: 4, planguage: 'C', score: '75%' },
        { id: 5, planguage: 'HTML+CSS', score: '50%' },
        { id: 6, planguage: 'MySQL', score: '50%' },
        { id: 7, planguage: 'PHP', score: '50%' },
      ],
      educations: [
        {
          id: 1,
          name: 'Bangkok University',
          high: 'UNIVERSITY',
          program:
            'School of Information Technology and Innovation (Computer Science)',
        },
        {
          id: 2,
          name: 'Krabyai Vongkusolkit Phitthayakhom School',
          high: 'HIGH SCHOOL',
          program: 'Science–Math',
        },
      ],
    };
  },
};
</script>
<style>
.txt-stroke {
  font-family: sans-serif;
  color: transparent;
  -webkit-text-stroke-width: 2px;
  -webkit-text-stroke-color: #fbaa33;
}
</style>

