<template>
<title>{{videos.title}}</title>
<div class="mx-1 p-3">
<a @click="click">      
      <img  class="hover:bg-red-100 rounded-full" src=".././../assets/back.svg">
    </a>
</div>
<div class="md:flex m-5">

  <div class="flex-1 flex-col max-w-2xl min-h-full">
    
    <div class="p-2 m-2">
        <!-- <video  id="video" width="700" height="500" controls class="rounded-2xl shadow-xl">
          <source :src='videosrc' type="video/mp4">
        </video> -->
        
        <vue-plyr :options="options" >
            <video 
                preload="auto"
                controls
                playsinline
                data-poster=""
            >
                <source
                :size='videos.size'
                :src='videosrc'
                :type='videos.type'
                />
                <track
                default
                kind="captions"
                label="English captions"
                src=""
                srclang="en"
                />
            </video>
            </vue-plyr>
            
    </div>
  
    <div class="flex justify-between items-center p-3 m-2">
      <div class="text-xl font-bold">{{video.title}}</div>
      <div class="flex">
      <div class="font-bold mr-3 mt-1"> {{Copytext}}</div>
      <div  class="font-normal min-w-18 text-white text-sm mr-3 bg-blue-400 p-2 rounded-lg" @click="sharelink">Copy Link</div>
      <div class="mr-2 mt-1"> <img class="viewsicon" src=".././../assets/akar-icons_eye.svg"></div>
      <div class="font-medium"> {{video.views}} Views </div>
      </div>
    </div>

    <div class="text-base font-medium p-4 m-2">
     {{video.desc}}
    </div>
</div>


<div class="flex-1">
    <CommentsVue/>
</div>

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
            videosrc:"",
            options:{quality:{default:'1080p'}},
            Copytext: '',
        }
    },
    props: {
        videos: {
            type: Object,
            default() {
            }
        },
    },
    methods:{
        updateVideo(val){
            this.videosrc=val
        },
        click(){
        // router.go(-1)
        router.push('/')
        },
        sharelink(){
            const currentURL = window.location.href;
            navigator.clipboard.writeText(currentURL);
            this.Copytext = 'Copied!'
        }
},
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