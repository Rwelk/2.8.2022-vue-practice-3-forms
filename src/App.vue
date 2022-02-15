<template>
  <div>
    <!-- Create a form  -->
    <form v-if="!submitted" action="">
      <!-- First name  -->
      <label>First Name:</label>
      <input type="text" required v-model="first_name">

      <!-- Last name  -->
      <label>Last Name:</label>
      <input type="text" required v-model="last_name">

      <!-- Email  -->
      <label>Email:</label>
      <input type="email" required v-model="email">

      <!-- Password (use a password field)  -->
      <label>Password:</label>
      <input type="password" required v-model="password">

      <!-- Store data checkbox – Yes/No  -->
      <label>Store data - Yes/No: </label>
      <input type="checkbox" name="check" id="check" v-model="checkbox">
      <br>

       
      <!-- Add a selection drop-down for Favorite Programming Language  -->
      <label>Favorite Language:</label>
      <select v-model="dropdown">
        <option value="python">Python</option>
        <option value="java">Java</option>
        <option value="c">C</option>
      </select>

      <button @click="submit">Submit</button>

    </form>
    
    <!-- Create a div/section that will display the results of the form data -->
    <div v-if="submitted" id="results">
      <p>First Name: {{ first_name }}</p>
      <p>Last Name: {{ last_name }}</p>
      <p>Email: {{ email }}</p>
      <p>Password: {{ password }}</p>
      <p>Checkbox: {{ checkbox }}</p>
      <p>Dropdown: {{ dropdown }}</p>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'App',
    data() {
      return {
        first_name: '',
        last_name: '',
        email: '',
        password: '',
        checkbox: false,
        dropdown: 'python',
        submitted: false,
      }
    },

    methods: {
      submit() {
        if (this.first_name && this.last_name && this.email && this.password)
        this.submitted = true
      }
    }
  }
</script>

<style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }

  form {
    max-width: 420px;
    margin: 30px auto;
    background: white;
    text-align: left;
    padding: 40px;
    border-radius: 10px;
  }

  label {
    color: #aaaaaa;
    display: inline-block;
    margin: 25px 0 15px;
    font-size: 1.1em;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-weight: bold;
    padding-right: 10px;
  }

  input, select {
    font-size: 1em;
    display: block;
    padding: 10px 6px;
    width: 100%;
    box-sizing: border-box;
    border: none;
    border-bottom: 1px solid #dddddd;
    color: #555555;
  }

  input[type="checkbox"] {
    display: inline-block;
    width: 20px;
    height: 20px;
    margin: 0 10px 0 0;
    position: relative;
    top: 1px;
  }

  button {
    margin: 30px;
    height: 50px;
    width: 100px;
    font-size: 1.1em;
  }
</style>
