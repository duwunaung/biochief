<template>
  <div class="register">
    <form @submit.prevent="handleSubmit">
      <label for="username">User Name: </label>
      <input
        type="text"
        placeholder="Your Profile Name"
        v-model="username"
        required
      />
      <label for="email">Email: </label>
      <input
        type="email"
        placeholder="name@example.com"
        v-model="email"
        required
      />
      <label for="password">Password: </label>
      <input
        type="password"
        placeholder="********"
        v-model="password"
        required
      />
      <label for="retype_password">Retype Password: </label>
      <input
        type="password"
        placeholder="********"
        v-model="retype_password"
        required
      />

      <label for="" class="error" v-if="error">***{{ error }}***</label>
      <div class="submit">
        <button>Create Account</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "Register",
  data() {
    return {
      username: "",
      email: "",
      password: "",
      retype_password: "",
      error: "",
    };
  },
  methods: {
    handleSubmit() {
      if (this.password == this.retype_password) {
        console.log("Successfully Created");
      } else {
        this.error = "Password not match!";
      }
    },
  },
};
</script>

<style>
form {
  max-width: 420px;
  margin: 30px auto;
  background: white;
  text-align: left;
  padding: 40px;
  border-radius: 10px;
}
label {
  color: #aaa;
  display: inline-block;
  margin: 25px 0 15px;
  font-size: 0.9em;
  text-transform: uppercase;
  letter-spacing: 1px;
  font-weight: bold;
}
input {
  display: block;
  width: 100%;
  padding: 10px 6px;
  widows: 100%;
  box-sizing: border-box;
  border: none;
  border-bottom: 1px solid #ddd;
  color: #555;
}
button {
  background: #0b6dff;
  border: 0;
  padding: 10px 20px;
  margin-top: 20px;
  color: white;
  border-radius: 20px;
}
.submit {
  text-align: center;
}
.error {
  font-size: 0.6em;
  color: red;
}
</style>