<template>
  <div>
    <form>
      <label for="imgInput"></label>
      <input id="imgInput" name="imageData" type="file" accept="image/*" @change="onChangeImg" />
    </form>
    <hr />
    <div class="img-display-area">
      <!-- <input type="button" value="[x]" @click="removeImgData" /> -->
      <img :src="imgDataURL"/>
    </div>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      imgDataURL : "",
    };
  },
  methods: {
    onChangeImg(e) {
      const file = e.target.files[0];
      const reader = new FileReader();
      reader.onload = event => {
        const result = event.target.result;
        console.log(result);
      }
      reader.readAsDataURL(file);
    },
  }
};
</script>

<style lang="scss" scoped>
input[type="file"] {
  border: none;
}
</style>
