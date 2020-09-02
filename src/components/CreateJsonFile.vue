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
      <tr>
        <td></td>
        <td>KEY</td>
        <td>VALUE</td>
      </tr>
      <tr v-for="(line, index) in lines" v-bind:key="index">
        <th>{{ index }}</th>
        <td><input v-model="line.key" type="text" placeholder="KEY" /></td>
        <td><input v-model="line.value" type="text" placeholder="VALUE" /></td>
      </tr>
    </table>

    <div>
      <code>{{ previewData }}</code>
      <input @click="createPreview" type="button" value="Preview" />
      <input @click="downloadJson" type="button" value="Download" />
    </div>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      lines: { 1: { key: "", value: "" } },
      previewData: "",
      valueType: "",
    };
  },
  methods: {
    getLinesLength: function(offset = 0) {
      const linesLength = Object.keys(this.lines).length;
      return linesLength + offset;
    },
    addNewRow: function() {
      const nextKey = this.getLinesLength(1);
      return this.$set(this.lines, nextKey, { key: "", value: "" });
    },
    removeRow: function() {
      if (this.getLinesLength() <= 1) {
        return void 0;
      } else {
        return this.$delete(this.lines, this.getLinesLength());
      }
    },
    downloadJson: function() {
      this.createPreview();
      // ダウンロード処理
      const data = this.previewData;
      console.log(this.previewData);
      const bom = new Uint8Array([0xef, 0xbb, 0xbf]);
      const blob = new Blob([bom, data], { type: "text/json" });
      const url = (window.URL || window.webkitURL).createObjectURL(blob);
      const link = document.createElement("a");
      link.download = "result.json";
      link.href = url;
      document.body.appendChild(link);
      link.click();
      document.body.removeChild(link);
      return console.log(this.previewData);
    },
    createPreview: function() {
      // JSONに整形
      const json = new Object();
      for (let index in this.lines) {
        const key = this.lines[index].key;
        const value = this.lines[index].value;
        json[key] = value;
      }
      return (this.previewData = JSON.stringify(json));
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/sass/_var.scss";
input,select {
  margin-right: 1rem;
}
input[type="text"] {
  margin-right: 1rem;
}
</style>
