<template>
  <div>
    <div class="imageupload-container" @click="open">
      <div v-if="!imageData">
        <div class="imageupload-text">
        <span class="fa-stack fa-lg">
          <i class="fa fa-photo fa-stack-2x"></i>
          <i class="fa fa-plus fa-stack-1x"></i>
        </span>
        </div>
      </div>
      <div v-else>
        <img :src="imageData" alt="">
      </div>
      <input type="file" ref="imagePicker" @change="handleChange">
    </div>
    <button type="button"
      class="btn btn-outline-primary btn-block"
      v-if="imageData"
      @click="remove">
      Zrušiť
    </button>
  </div>
</template>

<script>
export default {
  data () {
    return {
      file: null,
      imageData: null
    }
  },
  methods: {
    handleChange (e) {
      let input = e.target
      if (input.files && input.files[0]) {
        let reader = new FileReader()
        reader.onload = (e) => {
          this.imageData = e.target.result
        }
        reader.readAsDataURL(input.files[0])
        this.file = input.files[0]
      }
    },
    getData () {
      return this.file
    },
    open () {
      this.$refs.imagePicker.click()
    },
    remove () {
      this.file = null
      this.imageData = null
    }
  }
}
</script>

<style scoped>
input {
  display: none;
}
</style>
