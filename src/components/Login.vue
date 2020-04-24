<template>
  <div>
    <form class="login" @submit.prevent="login">
        <div>
            <div class="signupheader">Login
            <img src= "../assets/megalogo.png" style="float: right">
            </div>

            <div class="signuptxt"> Email<span style="color: red">*</span>
            <input required v-model="email" type="email" style="border:none"/>
            <img src= "../assets/mailgrey.png" style="float: right"></div>

            <div class="signuptxt"> Password<span style="color: red">*</span>
            <input required v-model="password" type="password" style="border:none"/>
            <img src= "../assets/lockgrey.png" style="float: right"></div>
            <br/>
            <button type="submit">Login</button>
        </div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: "",
      password: ""
    };
  },

  methods: {
    login: function() {
      let email = this.email;
      let password = this.password;
      this.$store
        .dispatch("login", { email, password })
        .then(() => this.$router.push("/profile"))
        .catch(err => console.log(err));
    }
  }
};
</script>

<style lang="scss" scoped>
.login {
  display: grid;
  grid-template-columns: repeat(1, 350px);
  grid-template-rows: 20px 65px;
  color: white;
  position: fixed;
  top: 26%;
  left: 45%;
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