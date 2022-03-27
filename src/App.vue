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
      const audio = new Audio('file://' + r[0])
      audio.play().then(value => {
        console.log(value)
      }).catch(res => {
        console.log(res)
      })
    }
  }
}
</script>
