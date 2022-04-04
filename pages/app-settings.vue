<template>
  <div class="app-wrapper">
    <div class="app-content pt-3 p-md-3 p-lg-4">
      <div class="container-xl">
        <h1 class="app-page-title">Settings</h1>
        <hr class="mb-4" />
        <div class="row g-4 settings-section">
          <div class="col-12 col-md-4">
            <h3 class="section-title">General</h3>
            <div class="section-intro">
              Settings section intro goes here. Lorem ipsum dolor sit amet,
              consectetur adipiscing elit. <a href="help.html">Learn more</a>
            </div>
          </div>
          <div class="col-12 col-md-8">
            <div class="app-card app-card-settings shadow-sm p-4">
              <div class="app-card-body">
                <form class="settings-form" @submit.prevent="generalForm">
                  <div class="mb-3 d-none">
                    <label for="setting-input-1" class="form-label"
                      >Business Name<span
                        class="ms-2"
                        data-container="body"
                        data-bs-toggle="popover"
                        data-trigger="hover"
                        data-placement="top"
                        data-content="This is a Bootstrap popover example. You can use popover to provide extra info."
                        ><svg
                          width="1em"
                          height="1em"
                          viewBox="0 0 16 16"
                          class="bi bi-info-circle"
                          fill="currentColor"
                          xmlns="http://www.w3.org/2000/svg"
                        >
                          <path
                            fill-rule="evenodd"
                            d="M8 15A7 7 0 1 0 8 1a7 7 0 0 0 0 14zm0 1A8 8 0 1 0 8 0a8 8 0 0 0 0 16z"
                          />
                          <path
                            d="M8.93 6.588l-2.29.287-.082.38.45.083c.294.07.352.176.288.469l-.738 3.468c-.194.897.105 1.319.808 1.319.545 0 1.178-.252 1.465-.598l.088-.416c-.2.176-.492.246-.686.246-.275 0-.375-.193-.304-.533L8.93 6.588z"
                          />
                          <circle cx="8" cy="4.5" r="1" /></svg></span
                    ></label>
                    <input
                      type="text"
                      class="form-control"
                      id="setting-input-1"
                      value="--"
                      required
                    />
                  </div>
                  <div class="mb-3">
                    <label for="setting-input-2" class="form-label"
                      >First name</label
                    >
                    <input
                      type="text"
                      class="form-control"
                      id="setting-input-2"
                      value="Steve Doe"
                      v-model="user.firstname"
                      required
                    />
                  </div>
                  <div class="mb-3">
                    <label for="setting-input-2" class="form-label"
                      >Last name</label
                    >
                    <input
                      type="text"
                      class="form-control"
                      id="setting-input-2"
                      value="Steve Doe"
                      v-model="user.lastname"
                      required
                    />
                  </div>
                  <div class="mb-3">
                    <label for="setting-input-3" class="form-label"
                      >Business Email Address</label
                    >
                    <input
                      type="email"
                      class="form-control"
                      id="setting-input-3"
                      value=""
                      v-model="user.email"
                      required
                    />
                  </div>
                  <div class="mb-3">
                    <label for="setting-input-2" class="form-label"
                      >Username</label
                    >
                    <input
                      type="text"
                      class="form-control"
                      id="setting-input-2"
                      v-model="user.username"
                      required
                    />
                  </div>
                  <button type="submit" class="btn app-btn-primary">
                    Save Changes
                  </button>
                </form>
              </div>
              <!--//app-card-body-->
            </div>
            <!--//app-card-->
          </div>
        </div>
        <!--//row-->
        <hr class="my-4" />
        <div class="row g-4 settings-section">
          <div class="col-12 col-md-4">
            <h3 class="section-title">Plan</h3>
            <div class="section-intro">
              Settings section intro goes here. Lorem ipsum dolor sit amet,
              consectetur adipiscing elit. <a href="help.html">Learn more</a>
            </div>
          </div>
          <div class="col-12 col-md-8">
            <div class="app-card app-card-settings shadow-sm p-4">
              <div class="app-card-body">
                <div class="mb-2"><strong>Current Plan:</strong> Pro</div>
                <div class="mb-2">
                  <strong>Status:</strong>
                  <span class="badge bg-success">Active</span>
                </div>
                <div class="mb-2"><strong>Expires:</strong> 2030-09-24</div>
                <div class="mb-4">
                  <strong>Invoices:</strong> <a href="#">view</a>
                </div>
                <div class="row justify-content-between">
                  <div class="col-auto">
                    <a class="btn app-btn-primary" href="#">Upgrade Plan</a>
                  </div>
                  <div class="col-auto">
                    <a class="btn app-btn-secondary" href="#">Cancel Plan</a>
                  </div>
                </div>
              </div>
              <!--//app-card-body-->
            </div>
            <!--//app-card-->
          </div>
        </div>
        <!--//row-->
        <hr class="my-4 d-none" />
        <div class="row g-4 settings-section d-none">
          <div class="col-12 col-md-4">
            <h3 class="section-title">Data &amp; Privacy</h3>
            <div class="section-intro">
              Settings section intro goes here. Morbi vehicula, est eget
              fermentum ornare.
            </div>
          </div>
          <div class="col-12 col-md-8">
            <div class="app-card app-card-settings shadow-sm p-4">
              <div class="app-card-body">
                <form class="settings-form">
                  <div class="form-check mb-3">
                    <input
                      class="form-check-input"
                      type="checkbox"
                      value=""
                      id="settings-checkbox-1"
                      checked
                    />
                    <label class="form-check-label" for="settings-checkbox-1">
                      Keep user app activity history
                    </label>
                  </div>
                  <!--//form-check-->
                  <div class="form-check mb-3">
                    <input
                      class="form-check-input"
                      type="checkbox"
                      value=""
                      id="settings-checkbox-2"
                      checked
                    />
                    <label class="form-check-label" for="settings-checkbox-2">
                      Keep user app preferences
                    </label>
                  </div>
                  <div class="form-check mb-3">
                    <input
                      class="form-check-input"
                      type="checkbox"
                      value=""
                      id="settings-checkbox-3"
                    />
                    <label class="form-check-label" for="settings-checkbox-3">
                      Keep user app search history
                    </label>
                  </div>
                  <div class="form-check mb-3">
                    <input
                      class="form-check-input"
                      type="checkbox"
                      value=""
                      id="settings-checkbox-4"
                    />
                    <label class="form-check-label" for="settings-checkbox-4">
                      Lorem ipsum dolor sit amet
                    </label>
                  </div>
                  <div class="form-check mb-3">
                    <input
                      class="form-check-input"
                      type="checkbox"
                      value=""
                      id="settings-checkbox-5"
                    />
                    <label class="form-check-label" for="settings-checkbox-5">
                      Aenean quis pharetra metus
                    </label>
                  </div>
                  <div class="mt-3">
                    <button type="submit" class="btn app-btn-primary">
                      Save Changes
                    </button>
                  </div>
                </form>
              </div>
              <!--//app-card-body-->
            </div>
            <!--//app-card-->
          </div>
        </div>
        <!--//row-->
        <hr class="my-4 d-none" />
        <div class="row g-4 settings-section d-none">
          <div class="col-12 col-md-4">
            <h3 class="section-title">Notifications</h3>
            <div class="section-intro">
              Settings section intro goes here. Duis velit massa, faucibus non
              hendrerit eget.
            </div>
          </div>
          <div class="col-12 col-md-8">
            <div class="app-card app-card-settings shadow-sm p-4">
              <div class="app-card-body">
                <form class="settings-form">
                  <div class="form-check form-switch mb-3">
                    <input
                      class="form-check-input"
                      type="checkbox"
                      id="settings-switch-1"
                      checked
                    />
                    <label class="form-check-label" for="settings-switch-1"
                      >Project notifications</label
                    >
                  </div>
                  <div class="form-check form-switch mb-3">
                    <input
                      class="form-check-input"
                      type="checkbox"
                      id="settings-switch-2"
                    />
                    <label class="form-check-label" for="settings-switch-2"
                      >Web browser push notifications</label
                    >
                  </div>
                  <div class="form-check form-switch mb-3">
                    <input
                      class="form-check-input"
                      type="checkbox"
                      id="settings-switch-3"
                      checked
                    />
                    <label class="form-check-label" for="settings-switch-3"
                      >Mobile push notifications</label
                    >
                  </div>
                  <div class="form-check form-switch mb-3">
                    <input
                      class="form-check-input"
                      type="checkbox"
                      id="settings-switch-4"
                    />
                    <label class="form-check-label" for="settings-switch-4"
                      >Lorem ipsum notifications</label
                    >
                  </div>
                  <div class="form-check form-switch mb-3">
                    <input
                      class="form-check-input"
                      type="checkbox"
                      id="settings-switch-5"
                    />
                    <label class="form-check-label" for="settings-switch-5"
                      >Lorem ipsum notifications</label
                    >
                  </div>
                  <div class="mt-3">
                    <button type="submit" class="btn app-btn-primary">
                      Save Changes
                    </button>
                  </div>
                </form>
              </div>
              <!--//app-card-body-->
            </div>
            <!--//app-card-->
          </div>
        </div>
        <!--//row-->
        <hr class="my-4" />
      </div>
      <!--//container-fluid-->
    </div>
    <app-footer v-if="$root.showHeader"></app-footer>
  </div>
</template>

<script>
module.exports = {
  components: {
    "app-footer": Vue.defineAsyncComponent(() =>
      loadModule("./components/app-footer.vue", OPTIONS)
    ),
  },
  data: function () {
    return {
      user: {
        id: null,
        firstname: "",
        lastname: "",
        username: "",
        roles: [],
        email: "",
      },
    };
  },
  mounted() {
    this.getMe();
  },
  methods: {
    getMe() {
      var thisComp = this;
      var root = this.$root;
      var app_token = localStorage.getItem(root.APP_TOKEN);

      console.log(app_token);

      if (app_token) app_token = JSON.parse(app_token); // Parse the json string value

      console.log(app_token);

      var options = {
        headers: {
          Authorization: `Bearer ${app_token ? app_token.token : ""}`,
        },
      };

      if (app_token) {
        axios
          .get(root.API_ROUTES.me, options)
          .then((response) => {
            console.log(response);
            thisComp.user = response.data;
          })
          .catch((error) => {
            let message =
              typeof error.response !== "undefined"
                ? error.response.data.message
                : error.message;
          })
          .finally(() => {
            console.log(thisComp.user);
          });
      }
    },
    generalForm(e) {
      e.preventDefault();

      // if (this.name && this.age) {
      //   return true;
      // }

      // this.errors = [];

      // if (!this.name) {
      //   this.errors.push("Name required.");
      // }
      // if (!this.age) {
      //   this.errors.push("Age required.");
      // }

      let thisComp = this;
      let root = this.$root;


      let toast = this.$toast;

      let bodyData = root.clone(thisComp.user);
      delete bodyData.id;

      let app_token = localStorage.getItem(root.APP_TOKEN);

      if (app_token) app_token = JSON.parse(app_token); // Parse the json string value
      var options = {
        headers: {
          Authorization: `Bearer ${app_token ? app_token.token : ""}`,
        },
      };

      // console.log( thisComp.user )
      // return

      axios
        .put(root.API_ROUTES.users + "/" + thisComp.user.id, bodyData, options)
        .then((result) => {
          console.log(result);
          toast.success("Data updated succefully", { position: "bottom" });
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
</style>