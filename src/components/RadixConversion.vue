<template>
  <div id="radixConversion">
    <input v-model.number="radix.decimal" type="text" />
    <div class="radix-output">
      <ul>
        <li>
          2進数<span>{{ radix.decimal.toString(2) }}</span>
        </li>
        <li>
          8進数<span>{{ radix.decimal.toString(8) }}</span>
        </li>
        <li>
          10進数<span>{{ radix.decimal }}</span>
        </li>
        <li>
          16進数<span>{{ radix.decimal.toString(16) }}</span>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      radix: {
        decimal: 0,
      },
    };
  },
};
</script>

<style scoped>
.radix-output ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
}
</style>
