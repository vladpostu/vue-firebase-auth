<template>
  <div>
    <h1>Dashboard</h1>
    <button id="sign_out" @click="signOut">Logout</button>
  </div>
</template>

<script>
import { getAuth } from "firebase/auth";

export default {
  methods: {
    signOut() {
      const auth = getAuth();
      auth
        .signOut()
        .then(() => {
          console.log("Sign Out completed");
          this.$router.push("/");
        })
        .catch((error) => console.log(error));
    },
  },
};
</script>
