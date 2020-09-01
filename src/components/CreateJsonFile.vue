<template>
  <div class="create-json-flie">
    <h2>JSON生成</h2>
    <table>
      <tr>
        <td>KEY</td>
        <td>VALUE</td>
        <td></td>
      </tr>
      <tr v-for="line in lines" :key="line">
        <td><input v-model="line.key" type="text" /></td>
        <td><input v-model="line.value" type="text" /></td>
        <td></td>
      </tr>
    </table>

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
    <div>
      <p>{{ lines }}</p>
      <input @click="downloadJson" type="button" value="Download" />
    </div>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      lines: {},
      valueType: "",
    };
  },
  methods: {
    addNewRow: function() {
      const nextObjectLength = Object.keys(this.lines).length + 1;
      const nextKey = "line" + nextObjectLength;
      this.$set(this.lines, nextKey, { key: "", value: "" });
      return console.log(this.lines, nextKey);
    },
    removeRow: function() {
      return console.log("Delete Line:");
    },
    downloadJson: function() {
      return console.log("Download");
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
