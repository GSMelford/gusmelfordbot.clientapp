<template>
  <form @submit.prevent="submitForm">
    <h3>Login</h3>

    <label for="telegramId">Telegram Id</label>
    <input
      type="text"
      placeholder="Ur telegram id"
      id="telegramId"
      v-model="telegramId"
      required
    />

    <label for="password">Password</label>
    <input
      type="password"
      placeholder="Password"
      id="password"
      v-model="password"
      required
    />

    <button>Log In</button>
  </form>
</template>

<script>
import axios from 'axios'

export default {
  name: 'LoginForm',
  data () {
    return {
      telegramId: '',
      password: ''
    }
  },
  methods: {
    submitForm: function () {
      axios({
        method: 'post',
        url: 'https://localhost:44387/system/login',
        headers: {},
        data: {
          TelegramId: this.telegramId,
          Password: this.password
        }
      }).then((response) => {
        if (response.status === 200) {
          window.location = '/Home'
        }
      })
    }
  }
}
</script>

<style>
*,
*:before,
*:after {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
form {
  height: 520px;
  width: 400px;
  background-color: rgba(0, 0, 0, 0.403);
  position: absolute;
  transform: translate(-50%, -50%);
  top: 50%;
  left: 50%;
  border-radius: 10px;
  backdrop-filter: blur(10px);
  border: 2px solid rgba(255, 255, 255, 0.1);
  box-shadow: 0 0 40px rgba(8, 7, 16, 0.6);
  padding: 50px 35px;
}
form * {
  font-family: 'Poppins', sans-serif;
  color: #ffffff;
  letter-spacing: 0.5px;
  outline: none;
  border: none;
}
form h3 {
  font-size: 32px;
  font-weight: 500;
  line-height: 42px;
  text-align: center;
}

label {
  display: block;
  margin-top: 30px;
  font-size: 16px;
  font-weight: 500;
}
input {
  display: block;
  height: 50px;
  width: 100%;
  background-color: rgba(206, 205, 205, 0.514);
  border-radius: 3px;
  padding: 0 10px;
  margin-top: 8px;
  font-size: 14px;
  font-weight: 300;
}
::placeholder {
  color: #e5e5e5;
}
button {
  margin-top: 50px;
  width: 100%;
  background-color: #ffffff;
  color: #080710;
  padding: 15px 0;
  font-size: 18px;
  font-weight: 600;
  border-radius: 5px;
  cursor: pointer;
}
</style>
