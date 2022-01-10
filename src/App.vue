<template>
  <div class="content">
    <div class="password-box">
      <h2>Password Generator</h2>
      <input type="text" name="" placeholder="Create password" id="password" readonly>
    </div>
    <div class="buttons">
      <button type="button" class="btn" v-on:click="generatePassword()">Generate</button>
      <button type="button" class="btn-copy" v-on:click="copyPassword()">Copy to clipboard</button>
    </div>
    <footer>
      provided by CherryFox © 2022
    </footer>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import generator from 'generate-password'


export default Vue.extend({
  name: 'App',
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
});
</script>

<style>
@import 'assets/styles/style.css';

input::placeholder {
  font-size: 20px;
}

.content {
  display: flex;
  height: 100vh;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  background-image: url("../src/assets/home_bg.png");
  background-repeat: no-repeat;
  background-size: cover;
}

.buttons {
  padding: 30px;
  flex-direction: row;
  justify-content: space-between;
}

.password-box h2 {
  color: #fff;
  text-align: center;
  margin-bottom: 30px;
}

.password-box #password {
  padding: 25px;
  user-select: none;
  height: 50px;
  width: 400px;
  border-radius: 18px;
  border: 3px #fff;
  outline: none;
  font-size: 18px;
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

footer {
  color: #fff;
  font-size: 18px;
}

</style>
