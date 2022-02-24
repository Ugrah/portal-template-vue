<template>
  <div class="container mb-5">
    <div class="row">
      <div class="col-12 col-md-11 col-lg-7 col-xl-6 mx-auto">
        <div class="app-branding text-center mb-5">
          <router-link to="/" class="app-logo">
            <img
              class="logo-icon me-2"
              src="assets/images/app-logo.svg"
              alt="logo"
            /><span class="logo-text">PORTAL</span>
          </router-link>
        </div>
        <!--//app-branding-->
        <div class="app-card p-5 text-center shadow-sm">
          <h1 class="page-title mb-4">
            404<br /><span class="font-weight-light">Page Not Found</span>
          </h1>
          <div class="mb-4">
            Sorry, we can't find the page you're looking for.
          </div>
          <!-- <a class="btn app-btn-primary" href="#">Back</a> -->
          <router-link to="/" class="btn app-btn-primary"
            >Go to Home</router-link
          >
        </div>
      </div>
      <!--//col-->
    </div>
    <!--//row-->
    <app-footer></app-footer>
  </div>
  <!--//container-->
</template>

<script>
module.exports = {
  data: function () {
    return {};
  },
  components: {
    "app-footer": Vue.defineAsyncComponent(() => loadModule('./components/app-footer.vue', OPTIONS)),
  }
};
</script>

<style scoped>
@media (min-width: 1200px) {
  .app-wrapper {
    margin-left: 0;
  }
}
</style>