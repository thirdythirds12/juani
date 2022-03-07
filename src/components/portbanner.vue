<template>
  <section id="portbanner">
    <div
      class="container-fluid d-flex align-items-center justify-content-center"
    >
      <div class="row">
        <div class="col-md-12">
          <img data-aos="flip-left" data-aos-duration="1500" :src="bannerContent.img" alt="port-img" />
          <h1  v-html="bannerContent.title" class="line-1 anim-typewriter"></h1>
          <p data-aos="fade-in" data-aos-duration="1500" v-html="bannerContent.subtitle"></p>
          <br />
          <i data-aos="fade-in" data-aos-duration="1500" :class="bannerContent.fontawesomeclass"></i>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "portbanner",
  props: ["banner-content"],

  
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
@import "../assets/styles/_website.scss";
#portbanner {
  background-image: url("../assets/img/banner.jpg");
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center center;
  .container-fluid {
    height: 70vh;
    @media screen and (max-width: 1366px), screen and (max-height: 687px) {
      height: 90vh;
    }
    h1 {
      color: $dirty-white;
      font-weight: bold;
      @media only screen and (max-width: 568px) {
        font-size: 9vw;
      }
    }
    p {
      color: $dirty-white;
    }
    img {
      height: auto;
      width: auto;
      padding-bottom: 2%;
      @media only screen and (max-width: 767px) {
        width: 50%;
      }
    }

    i {
      color: $dirty-white;
      font-size: 2rem;
    }
  }
  .line-1 {
    position: relative;
    width: 11em;
    margin: 0 auto;
    border-right: 2px solid rgba(255, 255, 255, 0.75);
    text-align: center;
    white-space: nowrap;
    overflow: hidden;
  }

  /* Animation */
  .anim-typewriter {
    animation: typewriter 3s steps(40) 0.5s 1 normal both,
      blinkTextCursor 500ms steps(40) infinite normal;
  }
  @keyframes typewriter {
    from {
      width: 0;
    }
    to {
      width: 10em;
    }
  }
  @keyframes blinkTextCursor {
    from {
      border-right-color: rgba(255, 255, 255, 0.75);
    }
    to {
      border-right-color: transparent;
    }
  }
}
</style>