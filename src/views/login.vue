<script>
import Footer from '@/components/Footer.vue';
</script>

<template>
  <div class="login-container">
    <div class="login-box">
      <h2>Login</h2>
      <form>
        <div class="input-group">
          <label for="email">Email</label>
          <input type="email" id="email" placeholder="email" />
        </div>
        <div class="input-group">
          <label for="password">Password</label>
          <input type="password" id="password" placeholder="password" />
        </div>
        <button type="submit" class="login-button">Login</button>
      </form>
      <a href="#" class="forgot-password">Forgot Password?</a>
    </div>
  </div>
    <Footer/>
</template>

<style scoped>
.login-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background: #f5f5f5;
  font-family: 'Poppins', sans-serif;
}

.login-box {
  background: #fff;
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 40px 50px;
  width: 360px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  text-align: center;
}

.login-box h2 {
  color: #333;
  margin-bottom: 25px;
  font-size: 22px;
}

.input-group {
  margin-bottom: 20px;
  text-align: left;
}

.input-group label {
  color: #555;
  display: block;
  margin-bottom: 6px;
  font-size: 14px;
}

.input-group input {
  width: 100%;
  padding: 10px 12px;
  border: 1px solid #ccc;
  border-radius: 6px;
  font-size: 14px;
  outline: none;
}

.input-group input:focus {
  border-color: #800000;
}

.login-button {
  width: 100%;
  padding: 10px;
  margin-top: 10px;
  background: #800000;
  border: none;
  border-radius: 6px;
  color: #fff;
  font-size: 15px;
  font-weight: 600;
  cursor: pointer;
}

.login-button:hover {
  background: #660000;
}

.forgot-password {
  display: inline-block;
  margin-top: 15px;
  color: #666;
  font-size: 13px;
  text-decoration: none;
}

.forgot-password:hover {
  color: #800000;
}
</style>
