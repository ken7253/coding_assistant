<template>
  <div id="app">
    <AppHeader />
    <RadixConversion />
    <ColorConversion />
    <CreateJsonFile />
    <AppFooter/>
  </div>
</template>

<script>
import AppHeader from "./components/AppHeader";
import AppFooter from "./components/AppFooter";

import RadixConversion from "./components/RadixConversion";
import ColorConversion from "./components/ColorConversion";
import CreateJsonFile from "./components/CreateJsonFile";

export default {
  name: "app",
  components: {
    AppHeader,
    AppFooter,
    RadixConversion,
    ColorConversion,
    CreateJsonFile,
  },
};
</script>

<style lang="scss">
@import "./assets/sass/_var.scss";
#app {
  margin-top: 50px;
}
</style>
