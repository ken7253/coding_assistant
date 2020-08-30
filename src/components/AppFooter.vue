<template>
  <div class="app-footer">
      <p>&#169; {{ yearNow }} ken7253.</p>
  </div>
</template>

<script>
export default {
    data: function(){
        return {
            yearNow: 0,
        }
    }
}
</script>

<style lang="scss" scoped>
@import "../assets/sass/_var.scss";
.app-footer {
    width: 100%;
    text-align: center;
}
</style>