<template>
  <!-- Home Page
      This page shows all the videos in a grid list.
      Each element contains a video informaion such as thumbnail, title, time.
   -->
  <div class="flex " v-if="this.$route.path === '/'" >
        <ul>
          <div class="mt-6 flex space-x-6 flex-wrap px-6">
             <li 
                v-for="i in videos"
                :key= "i.id">
              <div class="sm:p-3 md:p-2 rounded-2xl transform transition duration-500 hover:scale-110">
                <router-link :to="`/videos/${i.id}`">
                  
                  <div class="relative">
                    <div class="relative">
                    <img :src=i.thumb class="shadow-lg rounded-md lg:rounded-2xl w-56 h-32 lg:w-64 lg:h-40" :title=i.title> 
                    </div>
                    <div class="absolute bottom-0 right-0 p-2 bg-gray-900 blur bg-opacity-50 rounded-tl-2xl rounded-br-2xl">
                    <p class="text-xl font-bold text-white drop-shadow-2xl">{{i.time}}</p>
                    </div>
                  </div>
                  <div class="text-gray-800 font-medium md:text-lg  lg:text-2xl text-center p-2 sm:text-lg">
                      <p class="drop-shadow-2xl">{{i.title}}</p>
                  </div>

              </router-link> 
            </div>
            </li>
          </div>

        </ul>

  </div>

  <!-- Router view to render Player -->
    <router-view 
        :videos="videos"
        />




</template>

<script>
import { testVideos } from "../../testVideos"
import router from "../../router"
export default {
  name: 'VideoHome',
  computed :{
    statusupdate(){
      return this.click()
    }
  },
  data() {
            return {
                videos:testVideos,
                thumbsrc:'',
                PageStatus:'',
            }
        },
  methods : {
     click() {  
      this.PageStatus = router.currentRoute.value
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

/* This style helps align the list. */
ul li:first-child {
  margin-left: 24px;
}

ul li:last-child {
  margin-right: 0px;
}
</style>
