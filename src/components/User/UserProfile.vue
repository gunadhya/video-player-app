<template>
  <div class="UserProfile">

      <h2>Name</h2> 
      <h3>{{name}}</h3>
      <h2>Email</h2> 
      <h3>{{email}}</h3>
      <button @click="click">Sign Out</button>
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
.UserProfile{
    margin-top: 5em;
}

</style>