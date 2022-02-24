<template>
  <!-- <div> -->
    <div class="search-mobile-trigger d-sm-none col">
      <i class="search-mobile-trigger-icon fas fa-search"></i>
    </div>
    <!--//col-->
    <div class="app-search-box col">
      <form class="app-search-form">
        <input
          type="text"
          placeholder="Search..."
          name="search"
          class="form-control search-input"
        />
        <button type="submit" class="btn search-btn btn-primary" value="Search">
          <i class="fas fa-search"></i>
        </button>
      </form>
    </div>
  <!-- </div> -->
</template>

<script>
export default {
  data: function () {
    return {};
  },
  mounted() {
    this.loadSearchBox();
  },
  methods: {
    loadSearchBox() {

      /* ====== Mobile search ======= */
      const searchMobileTrigger = document.querySelector(
        ".search-mobile-trigger"
      );
      const searchBox = document.querySelector(".app-search-box");

      searchMobileTrigger.addEventListener("click", () => {
        searchBox.classList.toggle("is-visible");

        let searchMobileTriggerIcon = document.querySelector(
          ".search-mobile-trigger-icon"
        );

        if (searchMobileTriggerIcon.classList.contains("fa-search")) {
          searchMobileTriggerIcon.classList.remove("fa-search");
          searchMobileTriggerIcon.classList.add("fa-times");
        } else {
          searchMobileTriggerIcon.classList.remove("fa-times");
          searchMobileTriggerIcon.classList.add("fa-search");
        }
      });
    },
  }
};
</script>

<style scope>
</style>