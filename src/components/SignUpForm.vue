<template>
  <form>
    <label>Email</label>
    <input v-model="email" type="email" required />
    <label>Password</label>
    <input v-model="password" type="password" required />

    <label>number</label>
    <input v-model="number" type="number" required />

    <label>Role</label>
    <select class="" v-model="role">
      <option value="Full stack developer">Full stack developer</option>
      <option value="Back end developer">Back end developer</option>
      <option value="DevOps & Cloud">DevOps & Cloud</option>
      <option value="UX/UI designer">UX/UI designer</option>
    </select>

    <label>Your skills </label>
    <input type="text" @keypress="addSkill" v-model="tempSkill" />
    <div
      @click="handleClick(index)"
      class="skills"
      v-for="(skill, index) in skills"
      :key="skill">
      {{ skill }}
    </div>

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
      number: 0,
      role: "Full stack developer",
      terms: false,
      names: [],
      tempSkill: "",
      skills: [],
    };
  },
  methods: {
    addSkill(event) {
      if (event.key === "Enter") {
        this.skills.push(this.tempSkill);
        this.tempSkill = "";
        this.skills = [...new Set(this.skills)];
      }
    },
    handleClick(index) {
      console.log(index, "index");
      this.skills.splice(index, 1);
    },
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
.skills {
  display: inline-block;
  margin: 20px 10px 0 0;
  padding: 6px 12px;
  background: #eee;
  border-radius: 20px;
  font-size: 12px;
  letter-spacing: 1px;
  font-weight: bold;
  color: #777;
  cursor: pointer;
}
</style>
