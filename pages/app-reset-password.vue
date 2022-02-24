<template>
  <div>
    <div class="row g-0 app-auth-wrapper">
      <div class="col-12 col-md-7 col-lg-6 auth-main-col text-center p-5">
        <div class="d-flex flex-column align-content-end">
          <div class="app-auth-body mx-auto">
            <div class="app-auth-branding mb-4">
              <router-link class="app-logo" to="/">
                <img
                  class="logo-icon me-2"
                  src="assets/images/app-logo.svg"
                  alt="logo"
                />
              </router-link>
            </div>
            <h2 class="auth-heading text-center mb-4">Password Reset</h2>

            <div class="auth-intro mb-4 text-center">
              Enter your email address below. We'll email you a link to a page
              where you can easily create a new password.
            </div>

            <div class="auth-form-container text-left">
              <form class="auth-form resetpass-form">
                <div class="email mb-3">
                  <label class="sr-only" for="reg-email">Your Email</label>
                  <input
                    id="reg-email"
                    name="reg-email"
                    type="email"
                    class="form-control login-email"
                    placeholder="Your Email"
                    required="required"
                  />
                </div>
                <!--//form-group-->
                <div class="text-center">
                  <button
                    type="submit"
                    class="btn app-btn-primary btn-block theme-btn mx-auto"
                  >
                    Reset Password
                  </button>
                </div>
              </form>

              <div class="auth-option text-center pt-2">
                <router-link class="app-link" to="/login">Log in</router-link>
                <span class="px-2">|</span>
                <router-link class="app-link" to="/signup">Sign up</router-link>
              </div>
            </div>
            <!--//auth-form-container-->
          </div>
          <!--//auth-body-->
        </div>
      </div>
      <div class="col-12 col-md-5 col-lg-6 h-100 auth-background-col">
        <div class="auth-background-holder"></div>
        <div class="auth-background-mask"></div>
        <div class="auth-background-overlay p-3 p-lg-5">
          <div class="d-flex flex-column align-content-end h-100">
            <div class="h-100"></div>
          </div>
        </div>
        <!--//auth-background-overlay-->
      </div>
    </div>
    <app-footer></app-footer>
  </div>
</template>

<script>
module.exports = {
  data: function () {
    return {};
  },
  components: {
    "app-footer": Vue.defineAsyncComponent(() =>
      loadModule("./components/app-footer.vue", OPTIONS)
    ),
  },
};
</script>

<style scoped>
body {
  padding-top: 0 !important;
}
.auth-background-holder {
  background: url("./assets/images/background/background-3.jpg") no-repeat
    center center;
  background-size: cover;
  height: 100vh;
  min-height: 100%;
}
@media (min-width: 1200px) {
  .app-wrapper {
    margin-left: 0 !important;
  }
}
</style>