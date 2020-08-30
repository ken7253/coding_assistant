<template>
  <div class="app-footer">
    <p>
      &#169; -<time v-once>{{ getYearNow() }}</time> ken7253
    </p>
  </div>
</template>

<script>
export default {
  data: function() {
    return {};
  },
  methods: {
    getYearNow: function() {
      const getNowDate = new Date();
      return getNowDate.getFullYear();
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/sass/_var.scss";
.app-footer {
  position: fixed;
  bottom: 0;
  padding: 0.25rem 0 0.5rem 0;
  z-index: 1000;
  width: 100%;
  text-align: center;
  background-color: $color-text;
  color: $color-white;
  p {
    margin: 0;
    font-size: 0.75rem;
  }
}
</style>
