<template>
<div class="p-3">
<a @click="click">      
      <img src=".././../assets/back.svg">
    </a>
</div>
<div class="md:flex">

  <div class="flex flex-col max-w-2xl">
    
    <div class="flex p-2 m-2">
        <video width="700" height="500" controls class="rounded-2xl shadow-xl">
          <source :src='videosrc' type="video/mp4">
        </video>
    </div>

    <div class="flex justify-between items-center p-3 m-2">
      <div class="text-xl font-bold">{{video.title}}</div>
      <div class="flex">
      <div class="mr-2 mt-1"> <img class="viewsicon" src=".././../assets/akar-icons_eye.svg"></div>
      <div class="font-medium"> {{video.views}} Views </div>
      </div>
    </div>

    <div class="text-base font-medium p-4 m-2">
     {{video.desc}}
    </div>
</div>


<CommentsVue/>
</div>

</template>

<script>
import router from "../../router"
import CommentsVue from "../Comments/Comments.vue"




export default {
    components:{
        CommentsVue
    },
    data() {
        return {
            videosrc:""
        }
    },
    props: {
        videos: {
            type: Object,
            default() {
            }
        }
    },
    methods:{
        updateVideo(val){
            this.videosrc=val
        },
        click(){
        // router.go(-1)
        router.push('/')
}},
    computed: {
        video() {
            // return this.videos.value.find(x=> x.id === parseInt(this.$route.params.id,10))
            const vidres = this.videos.find(x => x.id === parseInt(this.$route.params.id, 10));
            this.updateVideo(vidres.source)
            return vidres
        },
        
    },

}
</script>

<style scoped>

</style>