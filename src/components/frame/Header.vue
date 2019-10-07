<template>
  <div>
    <b-navbar toggleable="lg" type="dark" class="bg-blue" variant="info">
      <b-navbar-brand href="#" class="text text-light" id="title">Blood</b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav v-if="auth.user == null">
        <!-- Right aligned nav items -->
        <b-navbar-nav class="ml-auto">
          <b-navbar-nav>
            <b-nav-item @click="redirect('/Login')" v-show="$route.path === '/Register' || $route.path === '/Login' ?  true: false"  class="text text-light" id="login">Login</b-nav-item>
            <b-nav-item @click="redirect('/Register')"  v-show="$route.path === '/Register' || $route.path === '/Login'?  true: false"   class="text text-light" id="signup">Sign Up</b-nav-item>
          </b-navbar-nav>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>
<style scoped lang="scss">
@import "assets/colors.scss";
#title {
  color: $mel !important;
}
</style>
<script>
import ROUTER from "router";
import AUTH from "services/auth"
export default {
  data(){
    return{
      auth: AUTH
    }
  },
  methods: {
    redirect(router) {
      ROUTER.push(router);
    }
  }
};
</script>
