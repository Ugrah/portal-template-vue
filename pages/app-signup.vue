<template>
  <div>
    <div class="row g-0 app-auth-wrapper">
      <div class="col-12 col-md-7 col-lg-6 auth-main-col text-center p-5">
        <div class="d-flex flex-column align-content-end">
          <div class="app-auth-body mx-auto">
            <div class="app-auth-branding mb-4">
              <router-link to="/" class="app-logo">
                <img
                  class="logo-icon me-2"
                  src="assets/images/app-logo.svg"
                  alt="logo"
                />
              </router-link>
            </div>
            <h2 class="auth-heading text-center mb-4">Sign up to Portal</h2>

            <div class="auth-form-container text-start mx-auto">
              <form class="auth-form auth-signup-form">
                <div class="email mb-3">
                  <label class="sr-only" for="signup-email">Your Name</label>
                  <input
                    id="signup-name"
                    name="signup-name"
                    type="text"
                    class="form-control signup-name"
                    placeholder="Full name"
                    required="required"
                  />
                </div>
                <div class="email mb-3">
                  <label class="sr-only" for="signup-email">Your Email</label>
                  <input
                    id="signup-email"
                    name="signup-email"
                    type="email"
                    class="form-control signup-email"
                    placeholder="Email"
                    required="required"
                  />
                </div>
                <div class="password mb-3">
                  <label class="sr-only" for="signup-password">Password</label>
                  <input
                    id="signup-password"
                    name="signup-password"
                    type="password"
                    class="form-control signup-password"
                    placeholder="Create a password"
                    required="required"
                  />
                </div>
                <div class="extra mb-3">
                  <div class="form-check">
                    <input
                      class="form-check-input"
                      type="checkbox"
                      value=""
                      id="RememberPassword"
                    />
                    <label class="form-check-label" for="RememberPassword">
                      I agree to Portal's
                      <router-link to="#" class="app-link"
                        >Terms of Service</router-link
                      >
                      <router-link to="#" class="app-link"
                        >Privacy Policy</router-link
                      >
                      >
                    </label>
                  </div>
                </div>
                <!--//extra-->

                <div class="text-center">
                  <button
                    type="submit"
                    class="btn app-btn-primary w-100 theme-btn mx-auto"
                  >
                    Sign Up
                  </button>
                </div>
              </form>
              <!--//auth-form-->

              <div class="auth-option text-center pt-2">
                Already have an account?
                <router-link to="/login" class="text-link">Log in</router-link>
              </div>
            </div>
          </div>
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
  background: url("./assets/images/background/background-2.jpg") no-repeat
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