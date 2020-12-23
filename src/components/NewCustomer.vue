<template>
  <p>New Customer Creation</p>
  <form @submit.prevent="handleSubmit">
    <label>Customer Name*</label>
    <input type="customername" v-model="customername" /> <br />
    <div v-if="customernameEmpty" class="error">{{ customernameEmpty }}</div>
    <label>Customer ID</label>
    <input type="customerid" v-model="customerid" /> <br />
    <label>Contact Number*</label>
    <input type="customerphnum" v-model="customerphnum" /> <br />
    <div v-if="customernphnumEmpty" class="error">
      {{ customernphnumEmpty }}
    </div>
    <label>GST Number</label>
    <input
      type="customergstnumber"
      v-model="customergstnumber"
      maxlength="16"
      minlength="16"
    />
    <br />
    <label>Address</label>
    <input type="customeraddress" v-model="customeraddress" /> <br />
    <label>State</label>
    <select v-model="State">
      <option value="kerala">Kerala</option>
      <option value="tamilnadu">Tamil Nadu</option>
    </select>

    <div class="submit">
      <button>Add Customer</button>
    </div>
  </form>
</template>

<script>
export default {};
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

p {
  text-align: left;
  color: white;
  font-size: 25px;
  font-weight: bold;
}
button {
  display: inline-block;
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
  color: red;
  margin-top: 10px;
  font-size: 0.8rem;
  font-weight: bold;
}

body {
  background-image: linear-gradient(Black, lightblue);
}
</style>