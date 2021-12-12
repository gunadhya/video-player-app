<template>

  <div class="bg-red-100 p-2 flex justify-center items-center rounded-b-2xl">
    <div class="flex-1">
      <div v-if="$router.currentRoute.value.path!=='/'" class="hover:bg-red-200 rounded-full w-8 ml-6">
      <a @click="click" >      
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
      <img src="./assets/carbon_user-avatar.svg" style="margin-bottom: 2px;"
      >
    </router-link>
  </div>
  </div>
  </div>  

  <div>
  <router-view/>
  </div>
</template>


<script>
import router from "./router"
export default {
  
    methods:{
   
        click(){
        // router.go(-1)
        router.push('/')
        },
}
}
</script>



<style>
/* @import url("https://vjs.zencdn.net/7.17.0/video-js.css"); */


/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin-left: 3em;
  margin-right: 3em;
} */

:root {
  --plyr-color-main: #f87171;
}
.plyr{
  border-radius: .75em;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.527);
}
</style>
