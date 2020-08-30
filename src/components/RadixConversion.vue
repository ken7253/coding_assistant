<template>
  <div id="radixConversion">
    <h2>基数変換</h2>
    <input v-model.number="decimal" type="text">
    <div class="radix-output">
      <ul>
        <li>
          2進数<span>{{ toBinary() }}</span>
        </li>
        <li>
          8進数<span>{{ toOctal() }}</span>
        </li>
        <li>
          10進数<span>{{ decimal }}</span>
        </li>
        <li>
          16進数<span>{{ toHexdecimal() }}</span>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
        decimal: 0,
    };
  },
  methods: {
    toBinary: function() {
      return this.decimal.toString(2);
    },
    toOctal: function() {
      return this.decimal.toString(8);
    },
    toHexdecimal: function() {
      return this.decimal.toString(16);
    }
  }
};
</script>

<style lang="scss" scoped>
@import "../assets/sass/_var.scss";
.radix-output ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
}
</style>
