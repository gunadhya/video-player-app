<template>
  <!-- Main navbar 
        Implements navigation for the main ui. Contains routes to pages Home, Upload, User.
   -->
  <div class="bg-red-100 p-2 flex justify-center items-center rounded-b-2xl">
    <div class="flex-1">
      <div v-if="$router.currentRoute.value.path!=='/'" class="hover:bg-red-200 rounded-full w-8 ml-6">
        <a @click="back" >      
          <img src="./assets/back.svg">
        </a>
    </div>
  </div>

  <div class="flex-1 mr-28">
    <div class="flex">
      <router-link class="p-2 mt-3 transform transition duration-400 hover:scale-110" to="/">
          <img src="./assets/akar-icons_home.svg">
      </router-link>

      <router-link class="mt-2 transform transition duration-400 hover:scale-125" to="/upload" >
        <img src="./assets/Upload.svg">
      </router-link> 
    
      <router-link class="p-2 mt-2 ml-1 transform transition duration-400 hover:scale-110" to="/user">
        <img src="./assets/carbon_user-avatar.svg" style="margin-bottom: 2px;">
      </router-link>
      </div>
    </div>
  </div>  

  <!-- Main View to render Home Page -->
  <div>
    <router-view/>
  </div>

</template>


<script>
import router from "./router"
export default {
  
    methods:{
        // to handle go back action, takes the user back to home page 
        back(){
        // router.go(-1)
        router.push('/')
        },
}
}
</script>



<style>

/* Styles for the video player */
:root {
  --plyr-color-main: #f87171;
}
.plyr{
    border-radius: .75em;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.527);
}
</style>
