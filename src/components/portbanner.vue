<template>
  <section id="portbanner">
    <div class="container py-5">
      <div class="row align-items-center g-4">
        <div class="col-lg-6 order-2 order-lg-1 text-left d-flex flex-column justify-content-center">
          <span class="hero-tag" data-aos="fade-up" data-aos-duration="1200">Creative Developer</span>
          <i class="hero-icon" data-aos="fade-up" data-aos-duration="1300" :class="bannerContent.fontawesomeclass"></i>
          <h1 class="line-1 anim-typewriter" data-aos="fade-up" data-aos-duration="1400" v-html="bannerContent.title"></h1>
          <h3 data-aos="fade-up" data-aos-duration="1500" v-if="bannerContent.name" v-html="bannerContent.name"></h3>
          <p data-aos="fade-up" data-aos-duration="1600" v-html="bannerContent.subtitle"></p>
        </div>
        <div class="col-lg-6 order-1 order-lg-2 text-center">
          <img class="hero-portrait" data-aos="zoom-in" data-aos-duration="1500" :src="bannerContent.img" alt="Juanito Llera Parafina III" />
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
  min-height: 90vh;
  display: flex;
  align-items: center;
  background:
    linear-gradient(rgba(7, 17, 31, 0.62), rgba(7, 17, 31, 0.82)),
    url("../assets/img/banner.jpg") center/cover no-repeat;
  color: $dirty-white;
  padding: 4rem 0;

  .container {
    position: relative;
    z-index: 1;
  }

  .hero-tag {
    display: inline-flex;
    align-self: flex-start;
    padding: 0.45rem 0.9rem;
    border: 1px solid rgba(255, 255, 255, 0.22);
    border-radius: 999px;
    background: rgba(255, 255, 255, 0.1);
    color: #edf6ff;
    text-transform: uppercase;
    letter-spacing: 0.18em;
    font-size: 0.78rem;
    margin-bottom: 0.75rem;
  }

  h1 {
    color: $dirty-white;
    font-weight: 800;
    line-height: 1.02;
    font-size: clamp(2.6rem, 6vw, 4.6rem);
    text-shadow: 0 8px 24px rgba(0, 0, 0, 0.22);
    margin-bottom: 0.75rem;
    @media only screen and (max-width: 568px) {
      font-size: 2.1rem;
    }
  }

  h3 {
    color: rgba(255, 255, 255, 0.92);
    font-size: clamp(1.05rem, 2vw, 1.45rem);
    margin-bottom: 1rem;
  }

  p {
    color: rgba(255, 255, 255, 0.92);
    font-size: 1.03rem;
    max-width: 35rem;
    margin-bottom: 0;
  }

  .hero-icon {
    color: $dirty-white;
    font-size: 2rem;
    margin-bottom: 0.45rem;
    opacity: 0.95;
  }

  .hero-portrait {
    width: min(100%, 420px);
    max-width: 100%;
    height: auto;
    border-radius: 1.25rem;
    box-shadow: 0 26px 40px rgba(0, 0, 0, 0.35);
    border: 1px solid rgba(255, 255, 255, 0.16);
  }

  .line-1 {
    position: relative;
    width: 11em;
    margin: 0;
    border-right: 2px solid rgba(255, 255, 255, 0.8);
    text-align: left;
    white-space: nowrap;
    overflow: hidden;
    @media only screen and (max-width: 991px) {
      margin: 0;
      text-align: left;
    }
  }

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
      border-right-color: rgba(255, 255, 255, 0.8);
    }
    to {
      border-right-color: transparent;
    }
  }
}
</style>