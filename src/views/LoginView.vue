<template>
  <div class="container">
    <form @submit.prevent="login">
      <h2>Login</h2>
      <div class="input">
        <label for="email">Email address</label>
        <input type="text" name="email" placeholder="email@adress.com" />
      </div>
      <div class="input">
        <label for="password">Password</label>
        <input type="password" name="password" placeholder="password123" />
      </div>

      <button type="submit" id="login_button">Login</button>
    </form>
  </div>
</template>

<script>
import { getAuth, signInWithEmailAndPassword } from "firebase/auth";

export default {
  data() {
    return {
      email: "",
      password: "",
    };
  },
  methods: {
    login(submitEvent) {
      this.email = submitEvent.target.elements.email.value;
      this.password = submitEvent.target.elements.password.value;

      const auth = getAuth();
      signInWithEmailAndPassword(auth, this.email, this.password)
        .then((userCredential) => {
          const user = userCredential.user;
          console.log(user);
          this.$router.push("/dashboard");
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
