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
  const requestBody = {
    credential: 'string@sting.com',
    password: 'string',
    code: '111111'
  };
  const response = await fetch('https://usnc.dev-webdevep.ru/auth-back/api/v2/login', {
    method: 'POST',
    mode: 'no-cors',
    headers: {
      'Content-Type': 'application/json',
      'X-Real-IP': 'string',
    },
    body: JSON.stringify(requestBody)
  });
  console.log(response);
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
