# Vue.JS-Image-Upload-Wrapper
A Vue.JS wrapper for JavaScript image upload

<ImageUpload ref="imageUpload"></ImageUpload>

### Submit from parent
```
let data = new FormData()
let file = this.$refs.imageUpload.getData()

if (file) data.append('image', file)
```

### Submit from inside
```
let data = new FormData()
let file = this.file
if (file) data.append('image', file)
```
