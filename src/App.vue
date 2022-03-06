<template>
  <div class="content">
    <PasswordBox/>
    <Buttons/>
    <Footer/>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Buttons from './components/Buttons.vue'
import PasswordBox from './components/PasswordBox.vue'
import Footer from './components/Footer.vue'

export default Vue.extend({
  name: 'App',
  components: {
    Buttons,
    PasswordBox,
    Footer
  },
});
</script>

<style>
@import 'assets/styles/style.css';

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
</style>
