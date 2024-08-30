<template>
  <form>
    <label>Email</label>
    <input v-model="email" type="email" required />
    <label>Password</label>
    <input v-model="password" type="password" required />

    <label>Email</label>
    <input v-model="email" type="email" required />
    <label>Role</label>
    <select class="" v-model="role">
      <option value="Full stack developer">Full stack developer</option>
      <option value="Back end developer">Back end developer</option>
      <option value="DevOps & Cloud">DevOps & Cloud</option>
      <option value="UX/UI designer">UX/UI designer</option>
    </select>

    <div class="terms">
      <input v-model="terms" type="checkbox" required />
      <label>Please accept terms and conditions</label>
    </div>
  </form>
</template>

<script>
export default {
  data() {
    return {
      email: "",
      password: "",
      role: "Full stack developer",
      terms: false,
    };
  },
};
</script>

<style>
form {
  max-width: 420px;
  margin: 30px auto;
  background: white;
  text-align: left;
  padding: 40px;
  border-radius: 10px;
}
label {
  color: #aaa;
  display: inline-block;
  margin: 25px 0 15px;
  font-size: 0.6em;
  text-transform: uppercase;
  letter-spacing: 1px;
  font-weight: bold;
}
input,
select {
  display: block;
  padding: 10px 6px;
  width: 100%;
  box-sizing: border-box;
  border: none;
  border-bottom: 1px solid #ddd;
  color: #555;
}
input[type="checkbox"] {
  display: inline-block;
  top: 2px;
  width: 16px;
  position: relative;
  margin: 0 10px 0 0;
}
</style>
