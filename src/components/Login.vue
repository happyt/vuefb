<template>
  <div class="login">
    <h3>Sign in</h3>
    <input type="text" v-model="email" placeholder="Email"><br/>
    <input type="password" v-model="password" placeholder="Password"><br/>
    <button v-on:click="login">Connect</button>
    <p>If you don't hve an account, you can 
      <router-link to="/sign-up">create one</router-link></p>
  </div>
</template>

<script>
import firebase from 'firebase'

export default {
  name: 'login',
  data: function () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    login: function () {
      firebase.auth().signInWithEmailAndPassword(this.email, this.password)
      .then(
        (user) => {
          this.$router.replace('hello')
        },
        (err) => {
          alert('Oops. ' + err.message)
        }
      )
    }
  }
}
</script>

<style scoped>
.login {
  margin-top: 20px;
}
input {
  margin: 10px 0;
  width: 20%;
  padding: 10px;
}
button {
  margin-top: 10px;
  width: 10%;
  cursor: pointer;
}
p {
  margin-top: 20px;
  font-size: 13px;
}
p a {
  text-decoration: underline;
  cursor: pointer;
}
</style>
