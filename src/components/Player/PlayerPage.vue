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
<div class="">

<div class=" flex m-3 items-center justify-center shadow-md  rounded-t-2xl p-4 flex-col">
    <h1 class="text-xl font-bold">Comments</h1>
    <div class="overflow-auto sm:h-64 md:h-96">
    <ul>
        <li class="text-xs font-semibold flex">
            <img class="w-8 h-8 mt-2 bg-yellow-200 rounded-full" src="../../assets/logo.png">
            <p class="p-2">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Placeat omnis soluta repellendus excepturi, veniam magnam eveniet non distinctio, sapiente explicabo error reprehenderit eos quam beatae nisi, eligendi veritatis libero quae. </p>
        </li>
        <li class="text-xs font-semibold flex">
            <img class="w-8 h-8 mt-2 bg-yellow-200 rounded-full" src="../../assets/logo.png">
            <p class="p-2">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Placeat omnis soluta repellendus excepturi, veniam magnam eveniet non distinctio, sapiente explicabo error reprehenderit eos quam beatae nisi, eligendi veritatis libero quae. </p>
        </li>
        <li class="text-xs font-semibold flex">
            <img class="w-8 h-8 mt-2 bg-yellow-200 rounded-full" src="../../assets/logo.png">
            <p class="p-2">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Placeat omnis soluta repellendus excepturi, veniam magnam eveniet non distinctio, sapiente explicabo error reprehenderit eos quam beatae nisi, eligendi veritatis libero quae. </p>
        </li>
        <li class="text-xs font-semibold flex">
            <img class="w-8 h-8 mt-2 bg-yellow-200 rounded-full" src="../../assets/logo.png">
            <p class="p-2">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Placeat omnis soluta repellendus excepturi, veniam magnam eveniet non distinctio, sapiente explicabo error reprehenderit eos quam beatae nisi, eligendi veritatis libero quae. </p>
        </li>
        <li class="text-xs font-semibold flex">
            <img class="w-8 h-8 mt-2 bg-yellow-200 rounded-full" src="../../assets/logo.png">
            <p class="p-2">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Placeat omnis soluta repellendus excepturi, veniam magnam eveniet non distinctio, sapiente explicabo error reprehenderit eos quam beatae nisi, eligendi veritatis libero quae. </p>
        </li>
        <li class="text-xs font-semibold flex">
            <img class="w-8 h-8 mt-2 bg-yellow-200 rounded-full" src="../../assets/logo.png">
            <p class="p-2">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Placeat omnis soluta repellendus excepturi, veniam magnam eveniet non distinctio, sapiente explicabo error reprehenderit eos quam beatae nisi, eligendi veritatis libero quae. </p>
        </li>
        <li class="text-xs font-semibold flex">
            <img class="w-8 h-8 mt-2 bg-yellow-200 rounded-full" src="../../assets/logo.png">
            <p class="p-2">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Placeat omnis soluta repellendus excepturi, veniam magnam eveniet non distinctio, sapiente explicabo error reprehenderit eos quam beatae nisi, eligendi veritatis libero quae. </p>
        </li>
        <li class="text-xs font-semibold flex">
            <img class="w-8 h-8 mt-2 bg-yellow-200 rounded-full" src="../../assets/logo.png">
            <p class="p-2">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Placeat omnis soluta repellendus excepturi, veniam magnam eveniet non distinctio, sapiente explicabo error reprehenderit eos quam beatae nisi, eligendi veritatis libero quae. </p>
        </li>
        <li class="text-xs font-semibold flex">
            <img class="w-8 h-8 mt-2 bg-yellow-200 rounded-full" src="../../assets/logo.png">
            <p class="p-2">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Placeat omnis soluta repellendus excepturi, veniam magnam eveniet non distinctio, sapiente explicabo error reprehenderit eos quam beatae nisi, eligendi veritatis libero quae. </p>
        </li>
        <li class="text-xs font-semibold flex">
            <img class="w-8 h-8 mt-2 bg-yellow-200 rounded-full" src="../../assets/logo.png">
            <p class="p-2">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Placeat omnis soluta repellendus excepturi, veniam magnam eveniet non distinctio, sapiente explicabo error reprehenderit eos quam beatae nisi, eligendi veritatis libero quae. </p>
        </li>
        <li class="text-xs font-semibold flex">
            <img class="w-8 h-8 mt-2 bg-yellow-200 rounded-full" src="../../assets/logo.png">
            <p class="p-2">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Placeat omnis soluta repellendus excepturi, veniam magnam eveniet non distinctio, sapiente explicabo error reprehenderit eos quam beatae nisi, eligendi veritatis libero quae. </p>
        </li>
        <li class="text-xs font-semibold flex">
            <img class="w-8 h-8 mt-2 bg-yellow-200 rounded-full" src="../../assets/logo.png">
            <p class="p-2">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Placeat omnis soluta repellendus excepturi, veniam magnam eveniet non distinctio, sapiente explicabo error reprehenderit eos quam beatae nisi, eligendi veritatis libero quae. </p>
        </li>
    </ul>

</div>

</div>

<!-- comment form -->
<div class="flex m-3 items-center justify-center shadow-md rounded-b-md">
   <form class="w-full bg-white rounded-b-lg px-4 pt-2">
      <div class="flex flex-wrap -mx-3 mb-6">
         <div class="w-full md:w-full px-3 mb-2 mt-2">
            <textarea class="bg-red-100 rounded border border-red-100 leading-normal resize-none w-full h-20 py-2 px-3 font-medium placeholder-gray-700 focus:outline-none focus:bg-red-50" name="body" placeholder='Comment' required></textarea>
         </div>
         <div class="w-full md:w-full flex items-start md:w-full px-3">
            <div class="flex items-start w-1/2 text-gray-700 px-2 mr-auto">

            </div>
            <div class="-mr-1">
               <input type='submit' class="bg-white text-gray-700 font-medium py-1 px-4 border border-gray-400 rounded-lg tracking-wide mr-1 hover:bg-green-200" value='Send'>
            </div>
         </div>
         </div>
      </form>
   </div>
</div>

</div>

<!-- 
<div class="flex p-2 border mx-auto">
  comments
</div> -->

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

</style>