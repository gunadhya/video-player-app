<template>
  <div class="text-center">

    
<div class="m-8 py-4 px-8 bg-white shadow-lg rounded-lg my-20">
      <h2 class="text-lg font-bold p-3">Name</h2> 
      <h2 class="text-lg font-normal px-4">{{name}}</h2>
      <h2 class="text-lg font-bold p-3">Email</h2> 
      <h2 class="text-lg font-normal px-4">{{email}}</h2>
     
</div>
 <button @click="click" class="
        bg-red-500 px-5 py-3 text-sm shadow-sm font-medium tracking-wider
    text-yellow-100 rounded-full hover:shadow-2xl hover:bg-red-700" >Sign Out</button>

    </div>

</template>

<script>
export default {
    data() {
        return{ 
            name:'',
            email:''
            }
        },

    created : function (){

        this.name = "Jane Doe"
        this.email = "janedoe@noemail.abc"

    },
    methods:{
        click(){
            alert('Sign Out requested')
        }
       
    }
            
}
</script>


<style scoped>
</style>