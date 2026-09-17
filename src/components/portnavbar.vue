<template>
  <section id="portnavbar">
    <nav class="navbar navbar-expand-lg">
      <button
        class="navbar-toggler"
        type="button"
        aria-controls="navbarSupportedContent"
        :aria-expanded="isMenuOpen.toString()"
        aria-label="Toggle navigation"
        @click="toggleMenu"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <a class="navbar-brand" href="#top" aria-label="Go to the top of the page">
        <img class="brand-logo" src="../assets/img/wani.png" alt="Juanito Llera Parafina III logo" />
      </a>
      <div v-if="isMenuOpen" class="navbar-backdrop" @click="closeMenu"></div>
      <div id="navbarSupportedContent" :class="['navbar-collapse', { 'is-open': isMenuOpen }]">
        <ul class="navbar-nav ml-auto">
          <li class="nav-item" v-for="(navbarContent, x) in navbarContent" :key="x">
            <a class="nav-link portnavsbtn" :href="navbarContent.url" @click="closeMenu">
              {{ navbarContent.text }}
              <span class="sr-only">(current)</span>
            </a>
          </li>
        </ul>
      </div>
    </nav>
  </section>
</template>

<script>
import $ from "jquery";
export default {
  name: "portnavbar",
  props: ["navbar-content"],
  data() {
    return {
      isMenuOpen: false,
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
    closeMenu() {
      this.isMenuOpen = false;
    },
  },
};
$(document).ready(function () {
  $(".portnavsbtn").on("click", function (event) {
    if (this.hash !== "") {
      event.preventDefault();
      var hash = this.hash;
      $("html, body").animate(
        {
          scrollTop: $(hash).offset().top,
        },
        800,
        function () {
          window.location.hash = hash;
        }
      );
    }
  });
});
</script>

<style scoped lang="scss">
@import "../assets/styles/_website.scss";

h3 {
  margin: 40px 0 0;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: $dirty-white;
  font-weight: bold;
}

.brand-logo {
  display: block;
  width: 180px;
  height: auto;
  margin: 0 auto 0.3rem;
  filter: none;
}
</style>