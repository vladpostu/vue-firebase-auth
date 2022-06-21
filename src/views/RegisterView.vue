<template>
  <div class="container">
    <form @submit.prevent="register">
      <h2>Register</h2>
      <div class="input">
        <label for="email">Email address</label>
        <input type="text" name="email" placeholder="email@adress.com" />
      </div>
      <div class="input">
        <label for="email">Password</label>
        <input type="password" name="email" placeholder="password123" />
      </div>

      <button type="submit" id="login_button">Login</button>
    </form>
  </div>
</template>
