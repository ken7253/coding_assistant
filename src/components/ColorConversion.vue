<template>
  <div class="color-conversion">
    <h2>カラーコード変換</h2>
    <input v-model="colorCode" type="text" />
    <input @click="moldNum" type="button" value="変換">
    <ul>
      <li>red:{{ rgbColor[0] }}</li>
      <li>green:{{ rgbColor[1] }}</li>
      <li>blue:{{ rgbColor[2] }}</li>
    </ul>
    <p>for CSS</p>
    <code>rgb({{ rgbColor[0] }},{{ rgbColor[1] }},{{ rgbColor[2] }})</code>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      colorCode: '',
      rgbColor:'0',
    };
  },
  methods: {
    moldNum: function() {
      const moldArr = this.colorCode.match(/.{2}/g);
      const outArr = [];
      moldArr.forEach((element) => {
        outArr.push(this.hexConv(element));
      });
      this.rgbColor = outArr;
    },
    hexConv: function(num) {
      const hexNum = "0x" + num;
      const parsed = parseInt(hexNum, 16);
      return parsed;
    },
  },
};
</script>

<style scoped></style>
