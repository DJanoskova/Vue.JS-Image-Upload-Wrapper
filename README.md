# Vue.JS-Image-Upload-Wrapper
A Vue.JS wrapper for JavaScript image upload

<ImageUpload ref="imageUpload"></ImageUpload>
  
let data = new FormData()
let file = this.$refs.imageUpload.getData()
if (file) data.append('image', file)  
