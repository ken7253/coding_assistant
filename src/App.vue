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

<style>
body {font-family: source-han-sans-japanese, sans-serif;margin: 0;}
</style>