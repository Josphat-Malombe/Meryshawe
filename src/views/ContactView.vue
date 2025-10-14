<script setup></script>

<template>
  <div class="head">
      <h1>Contact Us</h1>
  </div>
  <div class="contact">
  
    
    <form>
      <div class="form-group">
        <label for="name">Your Name:</label>
        <input type="text" id="name" name="name" required />
      </div>

      <div class="form-group">
        <label for="email">Your Email:</label>
        <input type="email" id="email" name="email" required />
      </div>

      <div class="form-group">
        <label for="phone">Phone Number:</label>
        <input type="tel" id="phone" name="phone" required />
      </div>

      <div class="form-group">
        <label for="subject">Subject:</label>
        <input type="text" id="subject" name="subject" required />
      </div>

      <div class="form-group">
        <label for="question">Question:</label>
        <textarea id="question" name="question" rows="4" required></textarea>
      </div>

      <button type="submit">Submit</button>
    </form>
  </div>
</template>

<style scoped>
.contact {
  max-width: 600px;
  margin: 60px auto;
  background: #fff;
  padding: 40px 50px;
  border-radius: 8px;
  border: 1px solid #ddd;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  font-family: "Poppins", sans-serif;
}


.head {
  width: 100%;
  background: black;
  color: white;
  text-align: center;
  padding-top: 100px;
 
}

.head h1 {
  font-size: 2.5rem;
  font-weight: 700;
  margin: 0;
  color:white;
}

form {
  display: flex;
  flex-direction: column;
}

.form-group {
  margin-bottom: 20px;
}

label {
  display: block;
  margin-bottom: 6px;
  font-size: 14px;
  color: #333;
}

input,
textarea {
  width: 100%;
  padding: 10px 12px;
  border: 1px solid #ccc;
  border-radius: 6px;
  font-size: 14px;
  outline: none;
}

input:focus,
textarea:focus {
  border-color: #800000;
}

button {
  background-color: #800000;
  color: white;
  border: none;
  border-radius: 6px;
  padding: 10px;
  font-size: 15px;
  font-weight: 600;
  cursor: pointer;
  margin-top: 10px;
}

button:hover {
  background-color: #660000;
}
</style>
