<template>
  <header class="app-header fixed-top">
    <div class="app-header-inner">
      <div class="container-fluid py-2">
        <div class="app-header-content">
          <div class="row justify-content-between align-items-center">
            <div class="col-auto">
              <a
                id="sidepanel-toggler"
                class="sidepanel-toggler d-inline-block d-xl-none"
                href="#"
              >
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="30"
                  height="30"
                  viewBox="0 0 30 30"
                  role="img"
                >
                  <title>Menu</title>
                  <path
                    stroke="currentColor"
                    stroke-linecap="round"
                    stroke-miterlimit="10"
                    stroke-width="2"
                    d="M4 7h22M4 15h22M4 23h22"
                  ></path>
                </svg>
              </a>
            </div>
            <!--//col-->
            
            <app-search-box></app-search-box>

            <div class="app-utilities col-auto">
              <app-header-notif></app-header-notif>

              <div class="app-utility-item">
                <router-link to="/settings" title="Settings">
                  <svg
                    width="1em"
                    height="1em"
                    viewBox="0 0 16 16"
                    class="bi bi-gear icon"
                    fill="currentColor"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      fill-rule="evenodd"
                      d="M8.837 1.626c-.246-.835-1.428-.835-1.674 0l-.094.319A1.873 1.873 0 0 1 4.377 3.06l-.292-.16c-.764-.415-1.6.42-1.184 1.185l.159.292a1.873 1.873 0 0 1-1.115 2.692l-.319.094c-.835.246-.835 1.428 0 1.674l.319.094a1.873 1.873 0 0 1 1.115 2.693l-.16.291c-.415.764.42 1.6 1.185 1.184l.292-.159a1.873 1.873 0 0 1 2.692 1.116l.094.318c.246.835 1.428.835 1.674 0l.094-.319a1.873 1.873 0 0 1 2.693-1.115l.291.16c.764.415 1.6-.42 1.184-1.185l-.159-.291a1.873 1.873 0 0 1 1.116-2.693l.318-.094c.835-.246.835-1.428 0-1.674l-.319-.094a1.873 1.873 0 0 1-1.115-2.692l.16-.292c.415-.764-.42-1.6-1.185-1.184l-.291.159A1.873 1.873 0 0 1 8.93 1.945l-.094-.319zm-2.633-.283c.527-1.79 3.065-1.79 3.592 0l.094.319a.873.873 0 0 0 1.255.52l.292-.16c1.64-.892 3.434.901 2.54 2.541l-.159.292a.873.873 0 0 0 .52 1.255l.319.094c1.79.527 1.79 3.065 0 3.592l-.319.094a.873.873 0 0 0-.52 1.255l.16.292c.893 1.64-.902 3.434-2.541 2.54l-.292-.159a.873.873 0 0 0-1.255.52l-.094.319c-.527 1.79-3.065 1.79-3.592 0l-.094-.319a.873.873 0 0 0-1.255-.52l-.292.16c-1.64.893-3.433-.902-2.54-2.541l.159-.292a.873.873 0 0 0-.52-1.255l-.319-.094c-1.79-.527-1.79-3.065 0-3.592l.319-.094a.873.873 0 0 0 .52-1.255l-.16-.292c-.892-1.64.902-3.433 2.541-2.54l.292.159a.873.873 0 0 0 1.255-.52l.094-.319z"
                    />
                    <path
                      fill-rule="evenodd"
                      d="M8 5.754a2.246 2.246 0 1 0 0 4.492 2.246 2.246 0 0 0 0-4.492zM4.754 8a3.246 3.246 0 1 1 6.492 0 3.246 3.246 0 0 1-6.492 0z"
                    />
                  </svg>
                </router-link>
              </div>
              <!--//app-utility-item-->

              <app-header-user></app-header-user>
            </div>
            <!--//app-utilities-->
          </div>
          <!--//row-->
        </div>
        <!--//app-header-content-->
      </div>
      <!--//container-fluid-->
    </div>
    <!--//app-header-inner-->

    <app-sidepanel></app-sidepanel>
  </header>
  <!--//app-header-->
</template>

<script>
export default {
  data: function () {
    return {};
  },
  components: {
    "app-sidepanel": Vue.defineAsyncComponent(() =>
      loadModule("./components/app-sidepanel.vue", OPTIONS)
    ),
    "app-search-box": Vue.defineAsyncComponent(() =>
      loadModule("./components/app-search-box.vue", OPTIONS)
    ),
    "app-header-notif": Vue.defineAsyncComponent(() =>
      loadModule("./components/app-header-notif.vue", OPTIONS)
    ),
    "app-header-user": Vue.defineAsyncComponent(() =>
      loadModule("./components/app-header-user.vue", OPTIONS)
    ),
  },
  mounted() {
    this.loadTemplateEvents();
  },
  methods: {
    loadTemplateEvents() {
      var _app = this;
      window.addEventListener("load", function () {
        _app.responsiveSidePanel();
      });

      window.addEventListener("resize", function () {
        _app.responsiveSidePanel();
      });

      // /* ====== Mobile search ======= */
      // const searchMobileTrigger = document.querySelector(
      //   ".search-mobile-trigger"
      // );
      // const searchBox = document.querySelector(".app-search-box");

      // searchMobileTrigger.addEventListener("click", () => {
      //   searchBox.classList.toggle("is-visible");

      //   let searchMobileTriggerIcon = document.querySelector(
      //     ".search-mobile-trigger-icon"
      //   );

      //   if (searchMobileTriggerIcon.classList.contains("fa-search")) {
      //     searchMobileTriggerIcon.classList.remove("fa-search");
      //     searchMobileTriggerIcon.classList.add("fa-times");
      //   } else {
      //     searchMobileTriggerIcon.classList.remove("fa-times");
      //     searchMobileTriggerIcon.classList.add("fa-search");
      //   }
      // });
    },
    responsiveSidePanel() {
      let sidePanel = document.getElementById("app-sidepanel");
      let w = window.innerWidth;
      if (w >= 1200) {
        // if larger
        //console.log('larger');
        sidePanel.classList.remove("sidepanel-hidden");
        sidePanel.classList.add("sidepanel-visible");
      } else {
        // if smaller
        //console.log('smaller');
        sidePanel.classList.remove("sidepanel-visible");
        sidePanel.classList.add("sidepanel-hidden");
      }
    },
  },
};
</script>

<style scope>
</style>