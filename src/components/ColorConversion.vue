<template>
  <div class="color-conversion">
    <input v-model="colorCode" type="text" />
  </div>
</template>

<script>
export default {
    data: function(){
        return {
            colorCode: 0
        }
    }
};
</script>

<style scoped></style>
