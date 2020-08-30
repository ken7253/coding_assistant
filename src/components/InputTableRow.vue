<template>
  <tr>
    <td>
      <input v-model.trim="content.jsonKey" type="text" placeholder="Key" />
    </td>
    <td>
      <input v-model.trim="content.jsonValue" type="text" placeholder="Value" />
    </td>
    <td>
      <input @click="removeThis" type="button" value="-" />
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
  methods: {
    removeThis: function(){
      return console.log('remove this element');
    }
  },
};
</script>

<style lang="scss" scoped></style>
