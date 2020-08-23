<template>
  <div id="app">
    <AppHeader />
    <RadixConversion />
    <ColorConversion />
    <CreateJsonFile />
  </div>
</template>

<script>
import AppHeader from "./components/AppHeader";
import RadixConversion from "./components/RadixConversion";
import ColorConversion from "./components/ColorConversion";
import CreateJsonFile from "./components/CreateJsonFile";

export default {
  name: "app",
  components: {
    AppHeader,
    RadixConversion,
    ColorConversion,
    CreateJsonFile,
  },
};
</script>

<style lang="scss"></style>
