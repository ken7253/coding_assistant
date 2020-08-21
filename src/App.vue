<template>
  <div id="app">
      <AppHeader/>
      <RadixConversion/>
      <ColorConversion/>
  </div>
</template>

<script>
import AppHeader from './components/AppHeader'
import RadixConversion from './components/RadixConversion'
import ColorConversion from './components/ColorConversion'

export default {
    name: 'app',
    components: {
        AppHeader,
        RadixConversion,
        ColorConversion,
    }
}
</script>

<style lang="scss">
</style>