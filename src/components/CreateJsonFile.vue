<template>
  <div class="create-json-flie">
    <h2>JSON生成</h2>
    <div>
      <select v-model="valueType">
        <option disabled value>select type</option>
        <option>text</option>
        <option>number</option>
        <option>object</option>
      </select>
      <input @click="addNewRow" type="button" value="+" />
      <input @click="removeRow" type="button" value="-" />
    </div>
    <table>
      <tr v-for="(line, index) in lines" v-bind:key="index">
        <th>{{ index }}</th>
        <td><input v-model="line.key" type="text" placeholder="KEY" /></td>
        <td><input v-model="line.value" type="text" placeholder="VALUE" /></td>
        <td></td>
      </tr>
    </table>

    <div>
      <code>{{ lines }}</code>
      <input @click="downloadJson" type="button" value="Download" />
    </div>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      lines: { 1: { key: "", value: "" } },
      valueType: "",
    };
  },
  methods: {
    addNewRow: function() {
      const nextObjectLength = Object.keys(this.lines).length + 1;
      const nextKey = nextObjectLength;
      return this.$set(this.lines, nextKey, { key: "", value: "" });
    },
    removeRow: function() {
      const linesLastNum = Object.keys(this.lines).length;
      if (linesLastNum <= 1) {
        return void 0;
      } else {
        return this.$delete(this.lines, linesLastNum);
      }
    },
    downloadJson: function() {
      return console.log("Download");
    },
    convertToJson: function() {
      const original = this.lines;
      // 元データをJSONに変換
      return console.log(original);
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/sass/_var.scss";
input[type="text"] {
  margin-right: 1rem;
}
</style>
