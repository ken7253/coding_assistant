<template>
  <tr>
    <td>
      <input v-model.trim="content.jsonKey" type="text" placeholder="Key" />
    </td>
    <td>
      <input v-model.trim="content.jsonValue" type="text" placeholder="Value" />
    </td>
    <td>
      <input type="button" value="-" />
    </td>
  </tr>
</template>

<script>
export default {
  data: function() {
    return {
      content: {
        jsonKey: "",
        jsonValue: null,
      },
    };
  },
};
</script>

<style lang="scss" scoped></style>
