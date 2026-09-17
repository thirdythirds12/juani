<template>
  <section id="contact-me" class="portfolio-cta">
    <div class="container py-5">
      <div class="row align-items-end justify-content-between">
        <div class="col-12 mb-4">
          <h2 v-html="data.title"></h2>
        </div>
      </div>

      <div class="cta-links-row">
        <div class="cta-link-item" v-for="item in data.contents" :key="item.contactcontent">
          <i :class="item.fontawesomeclass"></i>
          <a :href="item.contactlink">{{ item.contactcontent }}</a>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "portcta",
  props: ["data"],
};
</script>

<style lang="scss">
@import "../assets/styles/_website.scss";

#contact-me {
  background: linear-gradient(180deg, #0a2a42 0%, #061d31 100%);
  color: white;
  padding: 4rem 0 5rem;

  h2 {
    color: white;
    font-size: clamp(2.5rem, 5vw, 4.2rem);
    line-height: 0.94;
    letter-spacing: -0.06em;
    margin: 0;
    font-weight: 800;
  }

  p {
    color: rgba(255, 255, 255, 0.75);
    line-height: 1.7;
    margin: 0;
  }

  .cta-links-row {
    display: grid;
    grid-template-columns: repeat(4, minmax(180px, 1fr));
    gap: 1rem;
    margin-top: 2.5rem;

    @media (max-width: 991px) {
      grid-template-columns: repeat(2, minmax(180px, 1fr));
    }

    @media (max-width: 575px) {
      grid-template-columns: 1fr;
    }
  }

  .cta-link-item {
    display: flex;
    align-items: center;
    gap: 0.75rem;
    background: rgba(255, 255, 255, 0.05);
    border: 1px solid rgba(255, 255, 255, 0.12);
    border-radius: 14px;
    padding: 0.95rem 1rem;

    i {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      width: 2.1rem;
      height: 2.1rem;
      border-radius: 10px;
      background: rgba(110, 195, 197, 0.18);
      color: #dff7f7;
      font-size: 1rem;
    }

    a {
      color: white;
      font-size: 0.98rem;
      font-weight: 600;
      text-decoration: none;
      word-break: break-word;
    }
  }
}
</style>