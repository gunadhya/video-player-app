<template>
<div class="playerpage">
    <a @click="click">      
      <img src=".././../assets/back.svg">
    </a>
    <div class="main">
    <div class="wholeplayer">
    <video class="player" width="400" controls :src='videosrc'></video>
        <div class="info">
            <div>
                <div class="title">
                    <h2>{{video.title}}</h2>
                <div class="views">
                    <img class="viewsicon" src=".././../assets/akar-icons_eye.svg">
                    <p style="display: inline-block">{{video.views}} Views</p>
                </div>
            </div>
                <p>{{video.desc}}</p>
            </div>
    
        </div>
    </div>
    <div class="commentsview">
        <h1>Comments</h1>
    </div>
    </div>
</div>
</template>

<script>
import router from "../../router"

export default {
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
 
.playerpage{
    margin-top:5em;
}
.title {
    display: flex;
    flex-direction: row;
}
.views {
margin-left: auto;}
.viewsicon{
    margin-right: 10px;

}
.main{
    display: flex;
}
.wholeplayer{
    padding: 1em;
}

.player{
    border-radius: 0.8em;
    width:400vh;
    max-width: 100%;
    min-width: 30%;
    height: auto;
    padding: .25em;
}

h2 {
    font-weight: 775;
    font-size: 4.0vh;
}
p {
    font-size: 3vmin;

}
a{
}
a:hover{
    cursor: pointer;
} 

@media screen and (max-width: 600px) {
  .commentsview {
    visibility: hidden;
    width: 100%;
    display: none;
  }
}
</style>