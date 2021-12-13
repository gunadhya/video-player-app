<template>
  <!-- Comments Section
    This section contains a list of previous comments and a new form to add comments to the video.
  -->
<div>

<div class=" flex m-3  justify-center shadow-md  rounded-t-2xl p-4 flex-col">
    <h1 class="text-xl font-bold ml-6">Comments</h1>
    <div id="scview" class="overflow-auto h-48 sm:h-60 md:h-96">
        <ul >
          <div class="mt-6 flex-col space-x-6 flex-wrap ">
             <li class="text-xs font-semibold flex"
                v-for="i in comments"
                :key= "i">
                
                            <img class="w-8 h-8 mt-2 bg-yellow-200 rounded-full" src="../../assets/logo.png">
                            <p class="p-2"> {{i.message}}</p>
                            </li>
          </div>

        </ul>
</div>

</div>

<!-- comment form -->
<div class="flex m-3 items-center justify-center shadow-md rounded-b-md">
   <form class="w-full rounded-b-lg px-4 pt-2" v-on:submit.prevent="onSubmit" >
      <div class="flex flex-wrap -mx-3 mb-6">
         <div class="w-full md:w-full px-3 mb-2 mt-2">
            <textarea v-model="comment" class="bg-red-100 rounded border border-red-100 leading-normal resize-none w-full h-20 py-2 px-3 font-medium placeholder-gray-700 focus:outline-none focus:bg-red-50" name="body" placeholder='Comment' required></textarea>
         </div>
         <div class="w-full flex items-start md:w-full px-3">
            <div class="flex items-start w-1/2 text-gray-700 px-2 mr-auto">

            </div>
            <div class="-mr-1">
               <button @click="commentup(comment)" class="bg-white text-gray-700 font-medium py-1 px-4 border border-gray-400 rounded-lg tracking-wide mr-1 hover:bg-green-200">Send</button>
            </div>
         </div>
         </div>
      </form>
   </div>
</div>


</template>

<script>
export default {
  name: 'Comments',
  data() {
      return {comment:''}
      },
    props:{
        comments:{user:'',message:''},
        commentup:Function
    }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    ul li:first-child {
  margin-left: 24px;
}

ul li:last-child {
  margin-right: 0px;
}
</style>
