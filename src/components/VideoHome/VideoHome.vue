<template>

  <div class="flex" v-if="this.$route.path === '/'" >
        <ul>
          <div class="mt-6 flex space-x-6 flex-wrap px-6">
             <li 
                v-for="i in videos"
                :key= "i.id">
              <div class="sm:p-3 md:p-2 rounded-2xl transform transition duration-500 hover:scale-110">
                <router-link :to="`/videos/${i.id}`">
                  
                  <div>
                    <img :src=i.thumb class="shadow-lg rounded-md lg:rounded-2xl w-56 h-32 lg:w-64 lg:h-40" :title=i.title> 
                  </div>
                  <div class="text-gray-800 font-medium md:text-lg  lg:text-2xl text-center p-2 sm:text-lg">
                      <p class="drop-shadow-lg">{{i.title}}</p>
                  </div>

              </router-link> 
            </div>
            </li>
          </div>

        </ul>

  </div>

    <router-view 
        :videos="videos"
        />




</template>

<script>
import { testVideos } from "../../testVideos"
import router from "../../router"
export default {


  name: 'VideoHome',
  
  props: {
    msg: String
  },
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

/* li:last-child {
  border-right: 30px solid orange;
} */

/* li:first-child {
  margin-left: 3vh;
} */
ul li:first-child {
  margin-left: 24px;
}

ul li:last-child {
  margin-right: 0px;
}
</style>
