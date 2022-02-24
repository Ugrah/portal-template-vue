<template>
  <div class="app-login">
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
            <h2 class="auth-heading text-center mb-5">Log in to Portal</h2>
            <div class="auth-form-container text-start">
              <form class="auth-form login-form" @submit.prevent="signinUser">
                <div class="email mb-3">
                  <label class="sr-only" for="signin-username">Username</label>
                  <input
                    id="signin-username"
                    name="signin-username"
                    type="text"
                    class="form-control signin-username"
                    placeholder="Email address"
                    required="required"
                    v-model="form.username"
                  />
                </div>
                <!--//form-group-->
                <div class="password mb-3">
                  <label class="sr-only" for="signin-password">Password</label>
                  <input
                    id="signin-password"
                    name="signin-password"
                    type="password"
                    class="form-control signin-password"
                    placeholder="Password"
                    required="required"
                    v-model="form.pass"
                  />
                  <div class="extra mt-3 row justify-content-between">
                    <div class="col-6">
                      <div class="form-check">
                        <input
                          class="form-check-input"
                          type="checkbox"
                          value=""
                          id="RememberPassword"
                          v-model="form.remember"
                        />
                        <label class="form-check-label" for="RememberPassword">
                          Remember me
                        </label>
                      </div>
                    </div>
                    <!--//col-6-->
                    <div class="col-6">
                      <div class="forgot-password text-end">
                        <router-link to="/reset-password"
                          >Forgot password?</router-link
                        >
                      </div>
                    </div>
                    <!--//col-6-->
                  </div>
                  <!--//extra-->
                </div>
                <!--//form-group-->
                <div class="text-center">
                  <button
                    type="submit"
                    class="btn app-btn-primary w-100 theme-btn mx-auto"
                  >
                    Log In
                  </button>
                </div>
              </form>

              <div class="auth-option text-center pt-2">
                No Account? Sign up
                <router-link to="/signup" class="text-link">here</router-link>
              </div>
            </div>
            <!--//auth-form-container-->
          </div>
          <!--//auth-body-->
        </div>
        <!--//flex-column-->
      </div>
      <!--//auth-main-col-->

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
    <!--//row-->
    <app-footer></app-footer>
  </div>
</template>

<script>
module.exports = {
  data: function () {
    return {
      errors: [],
      form: { username: "", pass: "", remember: false },
    };
  },
  components: {
    "app-footer": Vue.defineAsyncComponent(() =>
      loadModule("./components/app-footer.vue", OPTIONS)
    ),
  },
  methods: {
    signinUser() {

      let app = this;

      let toast = this.$toast;

      axios
        .post(API_ROUTES.auth, {
          username: this.form.username,
          password: this.form.pass,
        })
        .then((result) => {
          if (result.data.token) {
            app.$store.commit("LOGIN_SUCCESS", result.data);
            app.$router.push("/");
          }
        })
        .catch((error) => {
          let message =
            typeof error.response !== "undefined"
              ? error.response.data.message
              : error.message;
          toast.error(message, { position: "bottom" });
        });
    },
  },
};
</script>

<style scoped>
body {
  padding-top: 0 !important;
}
.auth-background-holder {
  background: url("./assets/images/background/background-1.jpg") no-repeat center center;
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