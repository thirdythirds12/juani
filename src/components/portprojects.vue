<template>
  <section id="projects" class="projects-section">
    <div class="container pb-5">
      <div class="row mb-4">
        <div class="col-lg-12">
          <h2 v-html="data.title" data-aos="fade-in" data-aos-duration="1000"></h2>
          <p  v-html="data.subtitle" data-aos="fade-in" data-aos-duration="1000"></p>
          <p class=" muted" data-aos="fade-in" data-aos-duration="1000">Projects I’ve led across healthcare, corporate, e-commerce, and digital marketing websites.</p>
        </div>
      </div>

      <ul class="nav nav-pills project-tabs" role="tablist" data-aos="fade-in" data-aos-duration="1000">
        <li class="nav-item" v-for="item in data.tabstitlecontents" :key="item.tabtitlelink">
          <a :class="item.tabtitleclass" data-toggle="tab" :href="item.tabtitlelink" role="tab">{{ item.tabtitle }}</a>
        </li>
      </ul>

      <div class="tab-content mt-4">
        <div
          v-for="group in data.tabscontent"
          :class="group.tabcontentclass"
          :id="group.tabcontentid"
          role="tabpanel"
          :key="group.tabcontentid"
        >
          <div class="row g-4">
            <article
              class="col-md-6 col-xl-4 mb-5"
              v-for="(item, index) in group.contents"
              :key="item.projecttitle + index"
              data-aos="fade-up"
              data-aos-duration="900"
            >
              <div class="project-card mb-2">
                <img class="project-card__image" :src="item.projectimg" alt="Project preview" />
                <div class="project-card__body">
                  <span class="project-chip">{{ item.projecttype }}</span>
                  <h5 v-html="item.projecttitle"></h5>
                  <p class="project-meta" v-html="item.projectyear"></p>
                  <p class="project-meta" v-html="item.projectposition"></p>
                  <a :href="item.projectlink" target="_blank" class="btn btn-port">Visit Website</a>
                </div>
              </div>
            </article>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "portprojects",
  props: ["data"],
  components: {},
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
@import "../assets/styles/_website.scss";

.projects-section {
  background: linear-gradient(180deg, rgba(255, 255, 255, 1), rgba(245, 248, 252, 0.98));
  color: $dark-blue;
  padding: 2rem 0 4rem;

  h2 {
    color: $dark-blue;
    font-weight: 800;
    margin-bottom: 0.75rem;
  }

  .eyebrow,
  .summary-pill {
    display: inline-flex;
    align-items: center;
    gap: 0.35rem;
    border-radius: 999px;
    padding: 0.35rem 0.75rem;
    background: rgba(17, 97, 126, 0.08);
    color: $blue-green;
    text-transform: uppercase;
    letter-spacing: 0.18em;
    font-size: 0.75rem;
    font-weight: 700;
  }

  .lead-text {
    color: #48607a;
    margin-bottom: 0;
  }

  .project-tabs {
    gap: 0.75rem;
    flex-wrap: wrap;
    justify-content: flex-start;
    @media (max-width: 767px) {
      justify-content: center;
    }

    .nav-item {
      margin: 0;
    }

    .nav-link {
      border-radius: 999px;
      color: $dark-blue;
      background: white;
      border: 1px solid #dfe7ef;
      padding: 0.65rem 1rem;
      font-weight: 700;
      transition: all 0.2s ease;

      &.active,
      &:hover {
        background: linear-gradient(135deg, $blue-green, $dark-blue);
        color: white;
        border-color: transparent;
        box-shadow: 0 12px 24px rgba(17, 97, 126, 0.18);
      }
    }
  }

  .project-card {
    display: flex;
    flex-direction: column;
    overflow: hidden;
    border-radius: 18px;
    background: white;
    border: 1px solid #e4ebf3;
    box-shadow: 0 14px 30px rgba(15, 23, 42, 0.08);
    height: 100%;
    transition: transform 0.2s ease, box-shadow 0.2s ease;

    &:hover {
      transform: translateY(-4px);
      box-shadow: 0 18px 34px rgba(15, 23, 42, 0.14);
    }

    &__image {
      width: 100%;
      height: 160px;
      object-fit: cover;
      display: block;
      border-bottom: 1px solid #edf3f8;
    }

    &__body {
      display: flex;
      flex: 1;
      flex-direction: column;
      padding: 1rem;
    }

    .project-chip {
      display: inline-block;
      border-radius: 999px;
      background: rgba(17, 97, 126, 0.08);
      color: $blue-green;
      font-size: 0.78rem;
      font-weight: 700;
      padding: 0.35rem 0.55rem;
      margin-bottom: 0.65rem;
      text-transform: uppercase;
      letter-spacing: 0.12em;
    }

    h5 {
      font-weight: 800;
      color: $dark-blue;
      font-family: $primary_font;
      margin-bottom: 0.35rem;
    }

    .project-meta {
      color: #48607a;
      margin-bottom: 0.25rem;
    }

    .btn-port {
      margin-top: auto;
      border-radius: 999px;
      background: linear-gradient(135deg, $blue-green, $dark-blue);
      color: white;
      border: none;
      padding: 0.6rem 0.95rem;
      font-weight: 700;
      transition: transform 0.2s ease, box-shadow 0.2s ease;

      &:hover {
        color: white;
        transform: translateY(-1px);
        box-shadow: 0 12px 20px rgba(17, 97, 126, 0.18);
      }
    }
  }
}
</style>