<template>
  <div id="app">
      <AppHeader/>
      <RadixConversion/>
  </div>
</template>

<script>
import AppHeader from './components/AppHeader'
import RadixConversion from './components/RadixConversion'

export default {
    name: 'app',
    components: {
        AppHeader,
        RadixConversion,
    }
}
</script>

<style>
body {font-family: source-han-sans-japanese, sans-serif;margin: 0;}
</style>