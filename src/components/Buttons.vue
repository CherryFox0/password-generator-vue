<template>
  <div class="buttons">
    <button type="button" class="btn" v-on:click="generatePassword()">Generate</button>
    <button type="button" class="btn-copy" v-on:click="copyPassword()">Copy to clipboard</button>
  </div>
</template>

<script lang="ts">
import generator from "generate-password";

export default {
  name: 'Buttons',
  methods: {
    generatePassword: function () {
      let randomLength = Math.floor(Math.random() * (30 - 20) + 20)
      //@ts-ignore
      document.getElementById('password').value = generator.generate({
        length: randomLength,
        numbers: true,
        symbols: true,
        uppercase: true
      })
    },
    copyPassword: function () {
      // @ts-ignore
      let copyText = document.getElementById("password")
      // @ts-ignore
      copyText.select()
      // @ts-ignore
      copyText.setSelectionRange(0, 999)
      document.execCommand("copy")
    }
  }
}
</script>

<style scoped>
.buttons {
  padding: 30px;
  flex-direction: row;
  justify-content: space-between;
}

.btn, .btn-copy {
  background: #ffa550;
  border: 2px solid #ffa550;
  height: 50px;
  width: 150px;
  border-radius: 15px;
  position: relative;
  cursor: pointer;
  font-family: "Roboto", sans-serif;
  margin: 10px;
  overflow: hidden;
  text-align: center;
  font-size: 18px;
  color: #fff;
  transition: ease-in-out 0.3s;
}

.btn:hover, .btn-copy:hover {
  background-color: #aaaaff;
}
</style>