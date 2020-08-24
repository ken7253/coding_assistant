<template>
  <div class="input-table-row">
    <tr>
      <td>
        <input v-model.trim="content.jsonKey" type="text" placeholder="Key" />
      </td>
      <td>
        <input
          v-model.trim="content.jsonValue"
          type="text"
          placeholder="Value"
        />
      </td>
      <td>
        <select v-model="content.valueType">
          <option disabled value="">select type</option>
          <option>text</option>
          <option>number</option>
          <option>object</option>
        </select>
      </td>
      <td>
        <!--
            <input type="button" value="+" @click="addNewRow" />
            <input type="button" value="-" @click="removeThisRow"/>
          -->
      </td>
    </tr>
  </div>
</template>

<script>
export default {
      data: function() {
    return {
      content: {
        jsonKey: "",
        jsonValue: null,
        valueType: "",
      },
    };
  },
};
</script>

<style lang="scss" scoped></style>
