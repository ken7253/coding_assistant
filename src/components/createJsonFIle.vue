<template>
  <div class="create-json-flie">
    <h2>JSON生成</h2>
    <table>
      <tr>
        <th><input type="text" placeholder="Key" /></th>
        <td><input type="text" placeholder="Value" /></td>
        <td>
            <select>
                <option value="text">text</option>
                <option value="number">number</option>
                <option value="object">object</option>
            </select>
        </td>
        <td>
            <input type="button" value="+" @click="addNewRow" />
            <input type="button" value="-" @click="removeThisRow"/>
        </td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  data: function() {
    return {};
  },
};
</script>

<style lang="scss" scoped></style>
