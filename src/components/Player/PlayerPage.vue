<template>
<!-- Main Player page
    Contains a video player, video information such as title, no of views, description.
    Has a copy link button which copies the current url to users clipboard.
    Also has a comments section.
    Video player is implemented using Plyr.io framework specially made for vue called vue-plyr.
 -->
<div class="md:flex m-5">
<!-- Video player section -->
  <div class="flex-1 flex-col max-w-2xl min-h-full">
    
    <div class="customplyr">       
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
      <div  class="hover:bg-blue-500 font-normal min-w-18 text-white text-sm mr-3 bg-blue-400 p-2 rounded-lg" @click="sharelink">Copy Link</div>
      <div class="mr-2 mt-1"> <img class="viewsicon" src=".././../assets/akar-icons_eye.svg"></div>
      <div class="font-medium"> {{video.views}} Views </div>
      </div>
    </div>

    <div class="text-base font-medium p-4 m-2">
        {{video.desc}}
    </div>
</div>

<!-- Comments section -->
<div class="flex-1">
    <CommentsVue/>
</div>

</div>

</template>

<script>
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
        sharelink(){
            const currentURL = window.location.href;
            navigator.clipboard.writeText(currentURL);
            this.Copytext = 'Copied!'
        }
},
    computed: {
        video() {
            const vidres = this.videos.find(x => x.id === parseInt(this.$route.params.id, 10));
            this.updateVideo(vidres.source)
            return vidres
        },
        
    },

}
</script>

<style scoped>
.customplyr{
    padding: .5em;
}

</style>