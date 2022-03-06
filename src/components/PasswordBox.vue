<template>
  <div class="password-box">
    <h2>Password Generator</h2>
    <input type="text" name="" placeholder="Create password" id="password" readonly>
  </div>
</template>

<script lang="ts">
export default {
  name: "Password-box"
}
</script>

<style scoped>
input::placeholder {
  font-size: 20px;
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
</style>