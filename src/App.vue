<template>
  <div id="app">
    <AppHeader />
    <main>
      <div class="content-box">
        <RadixConversion />
        <ColorConversion />
        <CreateJsonFile />
      </div>
    </main>
    <AppFooter />
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
main {
  max-width: 1000px;
  margin: 50px auto 0;
  .content-box {
    padding: 2.5vw;
    > div {
      margin: 10px;
      padding: 10px;
      border: solid 3px $color-theme;
      border-radius: 15px;
    }
  }
}
</style>
