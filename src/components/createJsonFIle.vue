<template>
  <div class="create-json-flie">
    <h2>JSON生成</h2>
    <table>
      <InputTableRow/>
    </table>
  </div>
</template>

<script>
import InputTableRow from "./InputTableRow";

export default {
  name: "CreateJsonFile",
  components: {
    InputTableRow,
  },
};
</script>

<style lang="scss" scoped></style>
