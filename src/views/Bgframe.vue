<template>
  <div>
    <div class="bggrey">
        <div class="header">Dont have an account?</div>
        <div class="header">Have an account?</div>
        <div class="greytxt"> Lorem ipsum dolor sit amet,<br> consectetur adipiscing elit, sed do<br> eiusmod tempor incididunt ut labore et<br> dolore magna aliqua.<br/>
        <button @click="$router.push('register')">Sign Up</button></div>
        <div class="greytxt"> Lorem ipsum dolor sit amet, consectetur<br> adipiscing elit.<br/><br/>
        <button @click="$router.push('login')">Login</button></div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.bggrey {
  display: grid;
  grid-template-columns: repeat(2, 460px);
  grid-template-rows: 100px 320px;
  color: white;
  position: fixed;
  top: 28%;
  left: 15%;
  width: 920px;
  height: 420px;
  background: rgba(35, 42, 59, 0.8);
  z-index: -1;
  button {
  border-radius: 50px;
  background-color: #4dabfe;
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
.header {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 25px;
  padding-top: 70px;
  padding-left: 110px;
  padding-bottom: 100px;
  text-align: left;
}
.header::after {
  border-bottom:#45a2fe 2px solid;
  width:25px;
  padding-top: 30px;
  background-color: transparent; 
  bottom: 5;
  content: '';
  display: block;
  left: 14%;
  width: 39px;
}
.greytxt {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 15px;
  padding-top: 65px;
  padding-left: 110px;
  text-align: left;
  line-height: 2;
}
</style>