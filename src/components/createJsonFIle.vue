<template>
  <div class="create-json-flie">
    <h2>JSON生成</h2>
    <table>
      <tr>
        <td>KEY</td>
        <td>VALUE</td>
        <td></td>
      </tr>
      <InputTableRow />
    </table>

    <div>
      <select v-model="valueType">
        <option disabled value="">select type</option>
        <option>text</option>
        <option>number</option>
        <option>object</option>
      </select>
      <input @click="addNewRow" type="button" value="+" />
    </div>
  </div>
</template>

<script>
import InputTableRow from "./InputTableRow";

export default {
  name: "CreateJsonFile",
  components: {
    InputTableRow,
  },
  data: function(){
    return {
      valueType: "",
    };
  },
  methods: {
    addNewRow: function(){
      return console.log(this.valueType,"add new row")
    },
  },
};
</script>

<style lang="scss" scoped></style>
