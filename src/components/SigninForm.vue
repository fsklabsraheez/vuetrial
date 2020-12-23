<template>
  <img src="@/assets/logo.png" />
  <p>Sign-In Form</p>
  <form @submit.prevent="handleSubmit">
    <label>UserName*</label>
    <input type="username" v-model="username" /> <br />
    <div v-if="usernameEmpty" class="error">{{ usernameEmpty }}</div>
    <label>Password*</label>
    <input type="password" v-model="password" />
    <div v-if="passwordEmpty" class="error">{{ passwordEmpty }}</div>
    <div v-if="passwordError" class="error">{{ passwordError }}</div>
    <label>Department</label>
    <select v-model="department">
      <option value="sales">Sales Department</option>
      <option value="purchase">Purchase Department</option>
    </select>
    <div class="submit">
      <button>Sign In</button>
    </div>
  </form>
</template>

<script>
export default {
  data() {
    return {
      username: "",
      password: "",
      department: "sales", //We pass the sales here to make the selection by default
      usernameEmpty: "",
      passwordEmpty: "",
      passwordError: "",
    };
  },
  methods: {
    handleSubmit() {
      if (this.username === "") {
        this.usernameEmpty = "UserName Required";
      }
      if (this.password === "") {
        this.passwordEmpty = "Password Required";
      }
      //Validate password length
      else {
        this.passwordError =
          this.password.length > 5
            ? ""
            : "Password Must be atleast 6 character length";
        this.passwordEmpty = "";
      }
    },
  },
};
</script>

<style>
form {
  display: block;
  width: 40%;
  height: 20%;
  margin: 30px auto;
  background: white;
  text-align: left;
  padding: 40px;
  border-radius: 10px;
}
label {
  color: #aaa;
  display: inline-block;
  margin: 20px 20px 15px 0px;
  font-size: 16px;
  text-transform: uppercase;
  letter-spacing: 1px;
  font-weight: bold;
}
input,
select {
  display: inline-block;
  padding: 10px 6px;
  margin: 10px auto 10px;
  width: 100%;
  box-sizing: border-box;
  border: none;
  border-bottom: 1px solid #ddd;
  color: #555;
  font-size: 15px;
}
img {
  margin: 0px 10px;
  width: 100px;
}

p {
  text-align: center;
  color: white;
  font-size: 25px;
  font-weight: bold;
}
button {
  background: blue;
  border: 0;
  padding: 10px 40px;
  font-size: 20px;
  margin-top: 20px;
  color: white;
  border-radius: 20px;
}
.submit {
  text-align: center;
}
.error {
  color: #ff0062;
  margin-top: 10px;
  font-size: 0.8rem;
  font-weight: bold;
}

body {
  background-image: linear-gradient(Black, lightblue);
}
</style>