<template>
  <div id="App">
    <button @click="showDialog" value="Click">Click Me</button>
  </div>
</template>

<script>
const { dialog } = require('electron').remote
export default {
  name: 'App',
  methods: {
    showDialog () {
      const r = dialog.showOpenDialogSync()
      console.log(r)
    }
  }
}
</script>
