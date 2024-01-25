<script setup>
import { ref } from 'vue';

const login = ref('');
const password = ref('');

const onLoginInput = (event) => {
  login.value = event.target.value;
}

const onPasswordInput = (event) => {
  password.value = event.target.value;
}

const auth = async (login, password) => {
  console.log(login, password);
}

const onAuthClick = () => {
  auth(login.value, password.value);
}
</script>

<template>
  <div>
    <input type="text" name="login" @input="onLoginInput">
    <input type="password" name="password" @input="onPasswordInput">
    <button type="button" @click="onAuthClick">Войти</button>
  </div>
</template>

<style scoped>
input,
button {
  display: block;
  margin-bottom: 10px;
}
</style>
