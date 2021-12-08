<template>
  <div id="nav">
    <div class="centerBar"> 
    <router-link class="centerBarItem" to="/">
      <img src="./assets/akar-icons_home.svg">
    </router-link>

    <router-link class="centerBarItem" to="/upload" >
      <img src="./assets/Upload.svg">
    </router-link> 
    
    <router-link class="centerBarItem" to="/user">
      <img src="./assets/carbon_user-avatar.svg" style="margin-bottom: 2px;"
      >
    </router-link>
</div>
  </div>
  <router-view/>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin-left: 3em;
  margin-right: 3em;
}

/* #nav { 
   display: flexbox;
   left: 0;
   top:0;
   margin: 20px;
   text-align: center;
} */

#nav {
  position: fixed;
  top: 0;
  left: 0;
  z-index: 9999;
  width: 100%;
  height: 50px;
  text-align: center;
  padding:.5em;
  background-color: rgba(255, 255, 255, 0.76);
}

.centerBar{
  position: relative;
  display: flexbox;
  height: max-content;
}

.centerBarItem {
  
padding-inline: 10px;
}
</style>
