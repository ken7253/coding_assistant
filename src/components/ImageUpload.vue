<template>
  <div>
    <form>
      <label for="imgInput"></label>
      <input id="imgInput" name="imageData" type="file" @change="onChangeImg" />
    </form>
    <hr />
    <div class="img-display-area">
      <input type="button" value="[x]" @click="removeImgData" />
      <div>
        <img
        v-show="uploadedImage"
        class="preview-item-file"
        :src="uploadedImage"
        alt=""
      /></div>
    </div>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      imgFileName: "",
    };
  },
  methods: {
    onChangeImg(e) {
      const files = e.target.files || e.dataTransfer.files;
      this.displayImg(files[0]);
    },
  }
};
</script>

<style lang="scss" scoped>
input[type="file"] {
  border: none;
}
</style>
