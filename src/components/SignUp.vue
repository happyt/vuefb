<template>
  <div class="sign-up">
    <h3>Create a new account,</h3>
    <input type="text" placeholder="Email"><br/>
    <input type="password" placeholder="Password"><br/>
    <button>Sign Up</button>
    <p>or go back to 
      <router-link to="/login">log in.</router-link></p>
  </div>
</template>

<script>
export default {
  name: 'signUp',
  data: function () {
    return {}
  },
  methods: {}
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
