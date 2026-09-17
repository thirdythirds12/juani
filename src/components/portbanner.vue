<template>
  <section id="portbanner">
    <div class="container py-5">
      <div class="row align-items-center g-4">
        <div class="col-lg-6 order-2 order-lg-1 text-left d-flex flex-column justify-content-center">
          <h1 class="line-1 anim-typewriter" data-aos="fade-up" data-aos-duration="1400" v-html="bannerContent.title"></h1>
          <h3 data-aos="fade-up" data-aos-duration="1500" v-if="bannerContent.name" v-html="bannerContent.name"></h3>
          <p data-aos="fade-up" data-aos-duration="1600" v-html="bannerContent.subtitle"></p>
          <div class="hero-actions" data-aos="fade-up" data-aos-duration="1700">
            <a href="#projects" class="btn btn-hero btn-hero--primary">View Projects</a>
            <a href="mailto:juaniparafina@gmail.com" class="btn btn-hero btn-hero--ghost">Let’s Talk</a>
          </div>
        </div>
        <div class="col-lg-6 order-1 order-lg-2 text-center pb-5">
          <div class="hero-portrait-wrap" data-aos="zoom-in" data-aos-duration="1500">
            <img class="hero-portrait" :src="bannerContent.img" alt="Juanito Llera Parafina III" />
          </div>
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

<style lang="scss">
@import "../assets/styles/_website.scss";

#portbanner {
  min-height: 88vh;
  display: flex;
  align-items: center;
  background:
    radial-gradient(circle at top left, rgba(110, 195, 197, 0.28), transparent 32%),
    linear-gradient(135deg, rgba(8, 28, 46, 0.96), rgba(12, 53, 74, 0.92)),
    url("../assets/img/banner.jpg") center/cover no-repeat;
  color: $dirty-white;
  padding: 4rem 0 5rem;

  .container {
    position: relative;
    z-index: 1;
  }

  .hero-badge {
    display: inline-flex;
    align-self: flex-start;
    background: rgba(255, 255, 255, 0.08);
    border: 1px solid rgba(255, 255, 255, 0.18);
    color: rgba(255, 255, 255, 0.9);
    border-radius: 999px;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    font-size: 0.72rem;
    font-weight: 700;
    padding: 0.55rem 0.8rem;
    margin-bottom: 1rem;
  }

  h1 {
    color: $dirty-white;
    font-weight: 800;
    line-height: 0.98;
    font-size: clamp(3rem, 6vw, 5rem);
    margin-bottom: 0.75rem;
    letter-spacing: -0.05em;
    text-shadow: 0 8px 24px rgba(0, 0, 0, 0.22);
    @media only screen and (max-width: 568px) {
      font-size: 2.6rem;
    }
  }

  h3 {
    color: rgba(255, 255, 255, 0.9);
    font-size: clamp(1.1rem, 2vw, 1.5rem);
    margin-bottom: 1rem;
    font-weight: 700;
  }

  p {
    color: rgba(255, 255, 255, 0.84);
    line-height: 1.7;
    font-size: 1.04rem;
    max-width: 34rem;
    margin-bottom: 1.6rem;
  }

  .hero-actions {
    display: flex;
    flex-wrap: wrap;
    gap: 0.9rem;
    margin-top: 0.25rem;

    .btn-hero {
      border-radius: 999px;
      padding: 0.85rem 1.3rem;
      font-size: 0.92rem;
      font-weight: 700;
      text-decoration: none;
      transition: transform 0.2s ease, box-shadow 0.2s ease, border-color 0.2s ease;

      &:hover {
        transform: translateY(-2px);
      }
    }

    .btn-hero--primary {
      background: linear-gradient(135deg, #e8f7ff, #c5f0ee);
      color: #0a2541;
      box-shadow: 0 14px 26px rgba(8, 31, 49, 0.2);
    }

    .btn-hero--ghost {
      border: 1px solid rgba(255, 255, 255, 0.32);
      background: rgba(255, 255, 255, 0.04);
      color: #eff7ff;
    }
  }

  .hero-portrait-wrap {
    position: relative;
    display: inline-block;
    padding: 0.9rem;
    border-radius: 2rem;
    background: linear-gradient(180deg, rgba(105, 198, 197, 0.24), rgba(8, 38, 58, 0.34));
    border: 1px solid rgba(255, 255, 255, 0.14);
    box-shadow: 0 24px 40px rgba(0, 0, 0, 0.18);
  }

  .hero-portrait {
    width: min(100%, 420px);
    max-width: 100%;
    height: auto;
    border-radius: 1.5rem;
    object-fit: cover;
    border: none;
    background: transparent;
    margin: 0 auto;
  }

  .line-1 {
    position: relative;
    width: 11em;
    margin: 0;
    border-right: 2px solid rgba(255, 255, 255, 0.85);
    white-space: nowrap;
    overflow: hidden;
    @media only screen and (max-width: 991px) {
      margin: 0;
    }

    @media only screen and (max-width: 600px) {
      width: auto;
      max-width: 100%;
      white-space: normal;
      overflow: visible;
      border-right: 0;
      animation: none;
    }
  }

  .anim-typewriter {
    animation:
      typewriter 3s steps(40) 0.5s 1 normal both,
      blinkTextCursor 500ms steps(40) infinite normal;
  }

  @keyframes typewriter {
    from { width: 0; }
    to { width: 10em; }
  }

  @keyframes blinkTextCursor {
    from { border-right-color: rgba(255, 255, 255, 0.85); }
    to { border-right-color: transparent; }
  }
}
</style>