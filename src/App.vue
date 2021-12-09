<template>


  <div class="bg-red-100 p-2 flex justify-center items-center rounded-b-2xl">
  <div class="flex items-center">
  <router-link class="p-2 transform transition duration-400 hover:scale-110" to="/">
      <img src="./assets/akar-icons_home.svg">
    </router-link>

        <router-link class="p-2 transform transition duration-400 hover:scale-125" to="/upload" >
      <img src="./assets/Upload.svg">
    </router-link> 
    
    <router-link class="p-2 mb-1 transform transition duration-400 hover:scale-110" to="/user">
      <img src="./assets/carbon_user-avatar.svg" style="margin-bottom: 2px;"
      >
    </router-link>
  </div>
  </div>  

  <div>
  <router-view/>
  </div>
</template>

<style>
/* @import url("https://vjs.zencdn.net/7.17.0/video-js.css"); */


/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin-left: 3em;
  margin-right: 3em;
} */
</style>
