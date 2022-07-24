<template>
  <div id="app">
    <keep-alive>
      <router-view v-if="$route.meta.keepAlive" :key="key" />
    </keep-alive>


    <router-view v-if="!$route.meta.keepAlive" :key="key" />

     <!-- <tab-bar v-if="$route.meta.showTab" /> -->

 <!-- <Login></Login> -->
<!-- <login-up></login-up> -->
  </div>
</template>

<script>
import TabBar from "./components/Tabbar";
import Login from "./views/login/signIn"
import LoginUp from "./views/login/signUp"

export default {
  components: {
    TabBar,
    Login,
    LoginUp
  },
  computed: {
    key() {
      return this.$route.fullPath;
    },
  },
};
</script>
