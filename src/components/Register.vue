<template>
  <div>
    <form @submit.prevent="register" class="bgsignup">
        <div>
            <div class="signupheader">Sign Up 
            <img src= "../assets/megalogo.png" style="float: right"></div>

            <div class="signuptxt"> Name<span style="color: red">*</span>
            <input style="border:none" id="name" type="text" v-model="name" required autofocus>
            <img src= "../assets/usergrey.png" style="float: right"></div>

            <div class="signuptxt"> Email<span style="color: red">*</span>
            <input style="border:none" id="email" type="email" v-model="email" required>
            <img src= "../assets/mailgrey.png" style="float: right"></div>

            <div class="signuptxt"> Password<span style="color: red">*</span>
            <input style="border:none" id="password" type="password" v-model="password" required>
            <img src= "../assets/lockgrey.png" style="float: right"></div>
            <br/>
            <button type="submit">Sign Up</button>
        </div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      email: "",
      password: "",
    };
  },

  methods: {
    register: function() {
      let data = {
        name: this.name,
        email: this.email,
        password: this.password,
      };
      this.$store
        .dispatch("register", data)
        .then(() => this.$router.push("/"))
        .catch(err => console.log(err));
    }
  }
};
</script>

<style lang="scss" scoped>
.bgsignup {
  display: grid;
  grid-template-columns: repeat(1, 350px);
  grid-template-rows: 20px 65px;
  color: white;
  position: fixed;
  top: 26%;
  left: 17%;
  width: 460px;
  height: 460px;
  background: white;
  button {
    border-radius: 50px;
    background-color: #f7902e;
    color: white;
    width: 140px;
    height: 50px;
    font-size: 0.8rem;
    font-weight: bold;
    letter-spacing: 1px;
    text-transform: uppercase;
    cursor: pointer;
  }
}
.signupheader {
  font-family: Arial, Helvetica, sans-serif;
  color: black;
  font-size: 25px;
  padding-top: 40px;
  padding-left: 110px;
  text-align: left;
}
.signupheader::after {
  border-bottom:#45a2fe 2px solid;
  width:25px;
  padding-top: 30px;
  content: '';
  display: block;
  left: 14%;
  width: 39px;
}
.signuptxt {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 15px;
  color: #798aae;
  padding-top: 65px;
  padding-left: 110px;
  text-align: left;
}
.signuptxt::after {
  border-bottom:#c4ccda 1px solid; 
  content: '';
  display: block;
  left: 14%;
  width: 220px;
}
</style>