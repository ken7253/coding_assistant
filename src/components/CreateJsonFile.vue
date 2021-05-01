<template>
  <div class="create-json-flie">
    <h2>JSON生成</h2>
    <div class="table-control">
      <select v-model="valueType">
        <option disabled value>select type</option>
        <option>text</option>
        <option>number</option>
        <option>boolean</option>
      </select>
      <input @click="addNewRow" type="button" value="+" />
      <input @click="removeRow" type="button" value="-" />
    </div>
    <table class="json-data-input">
      <tr>
        <td></td>
        <td>KEY</td>
        <td>VALUE</td>
      </tr>
      <tr v-for="(line, index) in lines" v-bind:key="index">
        <th>{{ index }}</th>
        <td><input v-model="line.key" type="text" placeholder="KEY" /></td>
        <td>
          <label v-if="line.valueType === 'boolean'">
            <input type="checkbox" v-model="line.value" />{{
              line.value
            }}</label
          >
          <input v-else v-model="line.value" type="text" placeholder="VALUE" />
        </td>
        <td>{{ line.valueType }}</td>
      </tr>
    </table>

    <div>
      <code>{{ previewData }}</code>
      <input @click="createPreview" type="button" value="Preview" />
      <input @click="downloadJson" type="button" value="Download" />
    </div>
    <div class="data-options">
      <h3>オプション</h3>
      <ul>
        <li>
          BOM:
          <label
            ><input v-model="jsonBOM" type="checkbox" /> {{ jsonBOM }}</label
          >
        </li>
        <li>filename: <input v-model="flieName" type="text" /></li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      lines: { 1: { key: "", value: "", valueType: "text" } },
      previewData: "",
      jsonBOM: false,
      flieName: "result",
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
      const type = this.valueType;
      return this.$set(this.lines, nextKey, {
        key: "",
        value: "",
        valueType: type,
      });
    },
    removeRow: function() {
      if (this.getLinesLength() <= 0) {
        return void 0;
      } else {
        return this.$delete(this.lines, this.getLinesLength());
      }
    },
    downloadJson: function() {
      this.createPreview();
      const data = this.previewData;
      const url = (window.URL || window.webkitURL).createObjectURL(
        this.checkBom(data)
      );
      const link = document.createElement("a");
      link.download = this.flieName + ".json";
      link.href = url;
      document.body.appendChild(link);
      link.click();
      document.body.removeChild(link);
      return console.log(this.previewData);
    },
    checkBom: function(data) {
      // BOMの有無を判定
      if (this.jsonBOM) {
        const bom = new Uint8Array([0xef, 0xbb, 0xbf]);
        const blob = new Blob([bom, data], { type: "application/json" });
        return blob;
      } else {
        const blob = new Blob([data], { type: "application/json" });
        return blob;
      }
    },
    createPreview: function() {
      // JSONに整形
      const json = new Object();
      for (let index in this.lines) {
        const key = this.lines[index].key;
        const value = this.lines[index].value;
        json[key] = value;
      }
      return (this.previewData = JSON.stringify(json, null, 4));
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/sass/_var.scss";
input,
select {
  margin-right: 1rem;
}
input[type="text"] {
  margin-right: 1rem;
}
.table-control {
  input[type="button"] {
    width: 40px;
    height: 40px;
    padding: 0;
    font-size: 1.25rem;
  }
}
.json-data-input {
  @include sp {
    width: 100%;
    th {
      width: 20px;
    }
    td {
      display: block;
      width: 100%;
      input {
        width: 100%;
      }
    }
  }
}
.data-options {
  ul {
    list-style-type: none;
    padding: 0;
  }
  label {
    cursor: pointer;
    margin: 0;
    input {
      margin: 0;
    }
  }
}
</style>
