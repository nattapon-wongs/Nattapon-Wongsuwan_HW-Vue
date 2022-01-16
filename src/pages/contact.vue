<template>
  <div class="container">
    <div class="Head w-screen h-80 relative bg-gray-900">
      <div class="absolute z-50">
        <div class="port">
          <div class="flex items-center justify-center w-screen h-80">
            <router-link :to="{ path: '/' }">
             <div class="title">
              <h1 class="text-5xl md:text-7xl font-extrabold text-white">
                <span class=" text-6xl md:text-8xl text-transparent bg-clip-text bg-gradient-to-tr from-yellow-600 to-yellow-500">PORT</span><span>FOLIO</span>
                </h1>
              </div>
            </router-link>
          </div>
        </div>
      </div>
      <div class="w-screen h-full">
        <img class="w-full h-full object-cover opacity-10"
          src="https://images.unsplash.com/photo-1571171637578-41bc2dd41cd2?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1740&q=80"
          alt="" />
      </div>
      <div class=" breakline bg-gradient-to-tr from-yellow-600 to-yellow-500 p-1 w-screen"></div>
    </div>

    <div class="Contact w-screen h-fit px-10 pt-10 pb-20 bg-gradient-to-r from-gray-100 to-gray-300" >
      <!-- Title -->
      <div class="flex justify-start my-10 md:m-20 items-end">
        <div class="txt">
          <h1 class="text-3xl md:text-5xl font-extrabold">
            CONTACT <span class="txt-stroke font-black">ME</span>
          </h1>
        </div>
        <div class="h-0.5 w-12 md:w-32 bg-yellow-400 mb-1.5"></div>
      </div>
      <!-- Data -->
      <div class="row my-10 ml-5 md:mx-40">
        <div v-for="cont in contacts" :key="cont.id">
          <div class="flex inline py-5">
            <h6 class="text-xl md:text-2xl font-extrabold">{{ cont.type }}
              <span class="text-base md:text-xl font-medium">: {{ cont.data }}</span>
            </h6>
          </div>
        </div>
      </div>
    </div>
  </div>
  <Footer />
</template>

<script>
import Footer from '../components/pfooter.vue';
export default {
  name: 'contact',
  components: {
    Footer: Footer,
  },
  data() {
    return {
      contacts: [
        { id: 1, type: 'Email', data: 'nattapon.wongs@bumail.net ' },
        { id: 2, type: 'Phone', data: '063-870-4411' },
        {
          id: 3,
          type: 'Address',
          data: '40/1 Village No.23 Thungluknok,Kamphaeng Saen,Nakhon Pathom 73140',
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
