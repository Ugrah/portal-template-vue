<template>
  <div class="app-utility-item app-user-dropdown dropdown">
    <a
      class="dropdown-toggle"
      id="user-dropdown-toggle"
      data-bs-toggle="dropdown"
      href="#"
      role="button"
      aria-expanded="false"
      ><img src="assets/images/user.png" alt="user profile"
    /></a>
    <ul class="dropdown-menu" aria-labelledby="user-dropdown-toggle">
      <li>
        <router-link to="/account" class="dropdown-item">Account</router-link>
      </li>
      <li>
        <!-- <a class="dropdown-item" href="settings.html">Settings</a> -->
        <router-link to="/settings" class="dropdown-item">Settings</router-link>
      </li>
      <li>
        <hr class="dropdown-divider" />
      </li>
      <li>
        <router-link to="#" class="dropdown-item" @click="logout()">Log Out</router-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data: function () {
    return {};
  },
  methods: {
    logout() {
      this.$store.commit('LOGIN_FAILLURE');
      this.$router.push('login');
    }
  },
};
</script>

<style scope>
</style>