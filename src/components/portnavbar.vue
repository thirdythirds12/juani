<template>
  <section id="portnavbar">
    <div class="row">
      <div class="col-md-12">
        <img src="../assets/img/wani.png" alt="" />
      </div>
    </div>
    <nav class="navbar navbar-expand-lg">
      <button
        class="navbar-toggler"
        type="button"
        data-toggle="collapse"
        data-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div
        class="collapse navbar-collapse text-center"
        id="navbarSupportedContent"
      >
        <ul class="navbar-nav mx-auto">
          <li
            class="nav-item active"
            v-for="(navbarContent, x) in navbarContent"
            :key="x"
          >
            <a class="nav-link portnavsbtn" :href="navbarContent.url"
              >{{ navbarContent.text }}<span class="sr-only">(current)</span></a
            >
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
};
$(document).ready(function () {
  // Add smooth scrolling to all links
  $(".portnavsbtn").on("click", function (event) {
    // Make sure this.hash has a value before overriding default behavior
    if (this.hash !== "") {
      // Prevent default anchor click behavior
      event.preventDefault();

      // Store hash
      var hash = this.hash;

      // Using jQuery's animate() method to add smooth page scroll
      // The optional number (800) specifies the number of milliseconds it takes to scroll to the specified area
      $("html, body").animate(
        {
          scrollTop: $(hash).offset().top,
        },
        800,
        function () {
          // Add hash (#) to URL when done scrolling (default click behavior)
          window.location.hash = hash;
        }
      );
    } // End if
  });
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
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
  color: $dark-blue;
  font-weight: bold;
}
.navbar-toggler-icon {
  background-image: url("data:image/svg+xml;charset=utf8,%3Csvg viewBox='0 0 32 32' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath stroke='rgba(55, 150, 131)' stroke-width='2' stroke-linecap='round' stroke-miterlimit='10' d='M4 8h24M4 16h24M4 24h24'/%3E%3C/svg%3E");
}
</style>