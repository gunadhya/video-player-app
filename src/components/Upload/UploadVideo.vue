<template>
  <div class="UploadVideo">

  <br/>
    
      
  <form @submit.prevent="submit">
      <h2>Title</h2>
        <input 
            v-model="title" 
        />
        <br/>
        <h3>Description</h3>
            <textarea
                cols="50"
                rows="10"
                v-model="description"
                />
        <br/>
    </form>
<button class="btn btn-info" @click="onPickFile">Upload</button>
            <input
            type="file"
            style="display: none"
            ref="fileInput"
            accept="video/*"
            @change="onFilePicked"/>
    <br/>
</div>

</template>

<script>
export default {
    data() {
        return{ 
                title:'',
                description:'',
                filepath:'',
            }
        },

    methods:{
        submit(filename){
                alert(` You have submitted ${this.title} & ${this.description} and the file is ${filename}`) 
                this.title = ''
                this.description = ''
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
.UploadVideo{
    margin-top: 2em;
    margin-bottom: 5em;
    
}
input {
    border-radius: .5em;
    width:100%;
      resize: vertical;

}

textarea {
    border-radius: .5em;
    width: 100%;
    resize: vertical;
}

.btn {
    width:100%;
    padding: .5em;
    border-radius: .5em;
    
}
</style>