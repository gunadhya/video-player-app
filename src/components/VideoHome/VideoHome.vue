<template>

  <div class="videohome" v-if="this.$route.path === '/'" >
  <ul>
    <li    
        v-for="i in videos"
        :key= "i.id"
>
    <router-link :to="`/videos/${i.id}`">
     
      <div class="card">
    <img :src=i.thumb class="preview" :title=i.title > 
      </div>
       <div class="container">
          <h4><b>{{i.title}}</b></h4>
        </div>

    </router-link> 
        </li></ul>

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
.videohome{
display: flexbox;
align-content: center;
top: 0;
left: 0;
margin-top: 5em;
}
h4 {
  font-size: 3.0vh;
  text-align: center;
  padding: 1px;
}
h2 {
  margin: 0px 0px 0px 0px;
  text-align: center;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #000000;
  text-decoration: none;

}

.preview{
    width: 35vh;
    height: 20vh;
    border-radius: .5em;
}

.card {
  /* Add shadows to create the "card" effect */
  box-shadow: 0 0 0 0 rgba(0,0,0,0.2);
  transition: 0.3s;
  border-radius: .5em;

}

/* On mouse-over, add a deeper shadow */
.card:hover {
  box-shadow: 0 0 0 0 rgb(0, 0, 0);
}

/* Add some padding inside the card container */
.container {
  padding: 2px 16px;
}
</style>
