<template>
<!-- Upload Page
    This page lets users upload an image with a title and description.
    The file picker only allows video files to be selected.
 -->

 
  <div class="flex flex-col m-12">      
  <form @submit.prevent="submit">
      <h2 class="text-lg font-bold p-3">Title</h2>
        <input class="bg-red-50 w-full p-2 rounded-2xl m-1 shadow-sm"
            v-model="title" 
        />
        <br/>
        <h2 class="text-lg font-bold p-3">Description</h2>
            <textarea class="bg-red-50 w-full p-2 rounded-2xl m-2 shadow-sm"
                cols="50"
                rows="10"
                v-model="description"
                />
        <br/>
    </form>
    <button class="bg-yellow-500 px-5 py-3 text-sm shadow-sm font-medium tracking-wider
    text-yellow-100 rounded-full hover:shadow-2xl hover:bg-yellow-600 ml-4" 
    @click="onPickFile">
    Upload</button>
            <input
            type="file"
            style="display: none"
            ref="fileInput"
            accept="video/*"
            @change="onFilePicked"/>
    <br/>
</div>
<div class="relative pt-1">
   <p class="pl-16 text-sm font-semibold text-gray-800">Upload in progress</p>    
  <div class="overflow-hidden h-2 mb-4 text-xs flex rounded bg-pink-200 ml-16 mr-16 mt-4">
      
    <div :style="{width:progress}" class="shadow-none flex flex-col text-center whitespace-nowrap text-white justify-center bg-pink-500"></div>
  </div>
</div>
</template>

<script>
export default {
    data() {
        return{ 
                title:'',
                description:'',
                filepath:'',
                progress:'10%',
            }
        },

    methods:{
        submit(filename){
                alert(` You have submitted ${this.title} & ${this.description} and the file is ${filename}`) 
                this.title = ''
                this.description = ''
                
                this.progress='50%'
            },

        onPickFile () {
            this.$refs.fileInput.click()
            },

            onFilePicked (event) {
            const files = event.target.files
            let filename = files[0].name
            const fileReader = new FileReader()
            fileReader.addEventListener('load', () => {
                this.imageUrl = fileReader.result
            })
            fileReader.readAsDataURL(files[0])
            this.image = files[0]
            this.submit(filename)
            }
    }
            
}
</script>


<style scoped>

</style>