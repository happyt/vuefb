<template>
  <div class="sign-up">
    <h3>Create a new account,</h3>
    <input type="text" v-model="email" placeholder="Email"><br/>
    <input type="password" v-model="password" placeholder="Password"><br/>
    <button v-on:click="signUp">Sign Up</button>
    <p>or go back to 
      <router-link to="/login">log in.</router-link></p>
  </div>
</template>

<script>
import firebase from 'firebase'

export default {
  name: 'signUp',
  data: function () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    signUp: function () {
      firebase.auth().createUserWithEmailAndPassword(this.email, this.password)
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
.signUp {
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
