<template>
  <div class="container">
    <form @submit.prevent="register">
      <h2>Register</h2>
      <div class="input">
        <label for="email">Email address</label>
        <input type="text" name="email" placeholder="email@adress.com" />
      </div>
      <div class="input">
        <label for="password">Password</label>
        <input type="password" name="password" placeholder="password123" />
      </div>

      <button type="submit" id="register_button">Register</button>
    </form>
  </div>
</template>

<script>
import { getAuth, createUserWithEmailAndPassword } from "firebase/auth";

export default {
  data() {
    return {
      email: "",
      password: "123456",
    };
  },
  methods: {
    register(submitEvent) {
      // data update
      this.email = submitEvent.target.elements.email.value;
      this.password = submitEvent.target.elements.password.value;

      // firebase registration
      const auth = getAuth();
      createUserWithEmailAndPassword(auth, this.email, this.password)
        .then((userCredential) => {
          const user = userCredential.user;
          console.log(user);
          console.log("Registration completed");
          this.$router.push("/");
        })
        .catch((error) => {
          const errorCode = error.code;
          const errorMessage = error.message;
          console.log(errorCode);
          console.log(errorMessage);
        });
    },
  },
};
</script>
