<template>
  <div>
    <img src="@/assets/logo.png" />
    <p>Sign In Form</p>
  </div>
  <form @submit.prevent="handleSubmit">
    <label>UserName</label>
    <input type="username" v-model="username" /> <br />
    <div v-if="usernameEmpty" class="error">{{ usernameEmpty }}</div>
    <label>Password</label>
    <input type="password" required v-model="password" />
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
      passwordError: "",
    };
  },
  methods: {
    handleSubmit() {
      if (this.username === "") {
        this.usernameEmpty.push("UserName Required");
      }
      //Validate password length
      this.passwordError =
        this.password.length > 5
          ? ""
          : "Password Must be atleast 6 character length";
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
  color: #555;
  font-size: 25px;
  font-weight: bold;
}
button {
  background: blue;
  border: 0;
  padding: 10px 20px;
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
</style>