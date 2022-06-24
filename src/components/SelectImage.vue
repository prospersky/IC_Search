<template>
  <div>
    <!-- <img :src='`https://www.gorilla-cannabis-seeds.co.uk/images/product_image_not_found.gif`'/> -->
    <!-- <img :src='`https://t1.daumcdn.net/cfile/tistory/99CB6F375A449E4A16`'/> -->
    <!-- <div class="imagePreviewWrapper" :style="{ 'background-image': `url(${previewImage})` }" @click="pickFile"> </div> -->
    <div class ="imagePreviewWrapper">
      <img :src='`${previewImage}`'  @click="selectImage"/>
    </div>
    <div>
       <input ref="fileInput" type="file" @input="pickFile">
    </div>
    <!-- <div style="padding:50px; position:relative;">
        <img :src='`https://t1.daumcdn.net/cfile/tistory/${imgName}`'
             @click="changeImg"/>
    </div> -->
  </div>
</template>
 
<script>
export default {
  data() {
    return {
      // previewImage:'/src/assets/product_image_not_found.gif',
      // previewImage:'https://t1.daumcdn.net/cfile/tistory/99CB6F375A449E4A16'
      previewImage:'https://www.gorilla-cannabis-seeds.co.uk/images/product_image_not_found.gif'
      // previewImage: null
      // imgName: '99CB6F375A449E4A16'
    }
  },
  methods: {
      selectImage () {
        console.log("click");
         this.$refs.fileInput.click()
      },
      pickFile () {
        let input = this.$refs.fileInput
        let file = input.files
        if (file && file[0]) {
          let reader = new FileReader
          reader.onload = e => {
            this.previewImage = e.target.result
          }
          reader.readAsDataURL(file[0])
          this.$emit('input', file[0])
        }
     }
  }
}
</script>
 
<style>
.imagePreviewWrapper {
    width: 250px;
    height: 250px;
    display: block;
    cursor: pointer;
    margin: 0 auto 30px;
    /* background-image: url('`https://www.gorilla-cannabis-seeds.co.uk/images/product_image_not_found.gif`'); */
    background-size: cover;
    background-position: center center;
}
</style>
