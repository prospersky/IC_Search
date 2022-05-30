<template>
  <div>
    picture select
    <button v-on:click="uploadPicture">Upload</button>
    <!-- <input id="input" type="file" accept="text/*" /> -->
    <input id="input" type="file" @change="onFileSelectd"/>
    <button @click="onUpload">Upload2</button>
  </div>

</template>

<script>

export default {
  data() {
    return {
      selectedFile: null
    }
  },
  methods: {
    uploadPicture() {
      console.log("click");
      var inputEl = document.querySelector("#input")
      inputEl.addEventListener("change", function (event) {
        // FileList
        var fileList = inputEl.files || event.target.files
        // File
        var file = fileList[0]
        var reader = new FileReader()
        reader.onload = function (progressEvent) {
          console.log(progressEvent.target.result)
        }
        reader.readAsText(file)
      })
    },
    onFileSelectd(event) {
      // console.log(event)
      this.selectedFile = event.target.files[0]
    },
    onUpload() {

    }
  }
}
</script>

<style scope>
  input {
    background-color: blue;
    vertical-align: middle;
  }
</style>
