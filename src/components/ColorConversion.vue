<template>
  <div class="color-conversion">
    <h2>カラーコード変換</h2>
    <input v-model="colorCode" type="text" />
    <input @click="moldNum" type="button" value="変換" />
    <ul>
      <li>red:{{ rgbColor[0] }}</li>
      <li>green:{{ rgbColor[1] }}</li>
      <li>blue:{{ rgbColor[2] }}</li>
    </ul>
    <p>for CSS</p>
    <p>{{ removeHashMark("#fff") }}</p>
    <code>rgb({{ rgbColor[0] }},{{ rgbColor[1] }},{{ rgbColor[2] }})</code>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      colorCode: "000000",
      rgbColor: [0, 0, 0],
    };
  },
  methods: {
    moldNum: function() {
      const removedHash = this.removeHashMark(this.colorCode);
      const checkedNum = this.checkNumLength(removedHash);
      const splitArr = checkedNum.match(/.{2}/g);
      const outputArr = [];
      splitArr.forEach((element) => {
        outputArr.push(this.hexConv(element));
      });
      this.rgbColor = outputArr;
    },
    removeHashMark: function(num) {
      const pattern = /^#/i;
      if (num.match(pattern)) {
        const arr = num.split('');
        arr.shift();
        return arr.join('');
      } else {
        return num;
      }
    },
    checkNumLength: function(num) {
      const numLength = num.length;
      if (numLength == 6) {
        return num;
      } else if (numLength == 3) {
        const arr = num.split('');
        const outputArr = [];
        arr.forEach((element) => {
          outputArr.push(element + element);
        });
        return outputArr.join('');
      } else {
        console.error(
          "error: An incorrect value has been entered as a color code."
        );
        return "000000";
      }
    },
    hexConv: function(num) {
      const hexNum = '0x' + num;
      const parsed = parseInt(hexNum, 16);
      return parsed;
    },
  },
};
</script>

<style scoped></style>
