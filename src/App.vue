<template>
  <div id="app">

    <keep-alive>
      <component v-bind:is="selectedComponent">
        <br>
        <br>
        <br>Component Not Found
      </component>
    </keep-alive>
    <transition name="view">
      <router-view/>
    </transition>
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/register">Register</router-link> |
      <router-link to="/login">Login</router-link>
      <span v-if="isLoggedIn"> | <a @click="logout">Logout</a></span>
      <span v-else> | 
        <router-link to="/login">Login</router-link>
        </span>
    </div>
  </div>
</template>


<script>
import Bgframe from './views/Bgframe.vue'
export default {
  computed: {
    isLoggedIn: function() {
      return this.$store.getters.isLoggedIn;
    }
  },
  methods: {
    logout: function() {
      this.$store.dispatch("logout").then(() => {
        this.$router.push("/login");
      });
    }
  },
  components: {
    Bgframe
  },
  data() {
    return {
      selectedComponent: "bgframe"
    };
  }
};
</script>

<style lang="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

.page {
  display: block;
  margin: 0 auto;
  width: 100%;
  max-width: 768px;
  padding: 15px;
  box-sizing: border-box;
}
// it kā swups labs esot bet nezinu vai var izmantot tpc dynamic comp
.view-enter-active, .view-leave-active {
  transition: opacity 0.5s ease-in-out, transform 0.5s ease;
  position: bottom;
}
.view-enter-active {
  transition-delay: 0.1s;
}
.view-enter {
  opacity: 0;
  transform: translateX(-70px);
}
.view-enter-to {
  opacity: 1;
  transform: translateX(0px);
}
.view-leave {
  opacity: 1;
  transform: translateX(70px);
}
.view-leave-to {
  opacity: 0;
  transform: translateX(-70px);
}
</style>
