<template>
  <section id="projects" class="projects-section">
    <div class="container pb-5">
      <div class="row mb-4 align-items-end">
        <div class="col-lg-12">
          <h2 v-html="data.title" data-aos="fade-in" data-aos-duration="1000"></h2>
          <p v-html="data.subtitle" data-aos="fade-in" data-aos-duration="1000"></p>
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
              <div class="project-card mb-2" @click="openProject(item)">
                <img class="project-card__image" :src="item.projectimg" alt="Project preview" />
                <div class="project-card__body">
                  <span class="project-chip">{{ item.projecttype }}</span>
                  <h5 v-html="item.projecttitle"></h5>
                  <p class="project-meta" v-html="item.projectyear"></p>
                  <p class="project-meta" v-html="item.projectposition"></p>
                  <div class="project-card__actions">
                    <button type="button" class="btn btn-port" @click.stop="openProject(item)">Project Info</button>
                    <a :href="item.projectlink" target="_blank" class="btn btn-port btn-port--ghost" @click.stop>Visit Website</a>
                  </div>
                </div>
              </div>
            </article>
          </div>
        </div>
      </div>
    </div>

    <div v-if="selectedProject" class="project-modal" @click.self="closeProject">
      <div class="project-modal__dialog" role="dialog" aria-modal="true">
        <button type="button" class="project-modal__close" @click="closeProject" aria-label="Close project info">&times;</button>

        <div class="project-modal__panel project-modal__panel--info">
          <div class="project-modal__info-block">
            <span class="project-modal__label">Role</span>
            <h3 v-html="selectedProject.projectposition"></h3>
          </div>

          <div class="project-modal__meta-grid">
            <div class="project-modal__meta-item">
              <span class="project-modal__label">Year</span>
              <strong v-html="selectedProject.projectyear"></strong>
            </div>

            <div class="project-modal__meta-item project-modal__meta-item--full">
              <span class="project-modal__label">Stack</span>
              <div v-if="selectedProject.projectstack && selectedProject.projectstack.length" class="project-modal__stack-icons">
                <span v-for="(tech, index) in selectedProject.projectstack" :key="tech + index" class="project-modal__tech-icon" :title="tech" aria-label="Tech stack icon">
                  <i v-if="tech.startsWith('fab ') || tech.startsWith('fas ')" :class="tech"></i>
                  <img v-else-if="tech.startsWith('http')" :src="tech" alt="Tech stack logo" class="project-modal__tech-logo" />
                </span>
              </div>
              <strong v-else>WordPress, PHP, JavaScript, CSS</strong>
            </div>

            <div class="project-modal__meta-item project-modal__meta-item--hosting">
              <span class="project-modal__label">Hosting</span>
              <strong>{{ selectedProject.projecthosting || 'Production web hosting' }}</strong>
            </div>
          </div>

          <div class="project-modal__actions">
            <a :href="selectedProject.projectlink" target="_blank" class="btn btn-port">Visit Website</a>
            <a href="mailto:juaniparafina@gmail.com?subject=Let%27s%20connect" class="btn btn-port btn-port--light">Let's connect</a>
          </div>
        </div>

        <div class="project-modal__panel project-modal__panel--visual">
          <div class="project-modal__browser">
            <div class="project-modal__browser-bar">
              <div class="project-modal__browser-dots">
                <span></span>
                <span></span>
                <span></span>
              </div>
            </div>
            <div class="project-modal__visual-hero" :style="{ backgroundImage: 'linear-gradient(rgba(8, 14, 22, 0.18), rgba(8, 14, 22, 0.18)), url(' + selectedProject.projectimg + ')' }"></div>
          </div>

          <div class="project-modal__feature-card">
            <span class="project-modal__feature-type">{{ selectedProject.projecttype }}</span>
            <h4 v-html="selectedProject.projecttitle"></h4>
            <p>{{ selectedProject.projectsummary || 'Custom website build and front-end implementation for a business-focused digital presence.' }}</p>
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
  data() {
    return {
      selectedProject: null,
    };
  },
  methods: {
    openProject(project) {
      this.selectedProject = project;
    },
    closeProject() {
      this.selectedProject = null;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
@import "../assets/styles/_website.scss";

.projects-section {
  background: linear-gradient(180deg, #f4efe9 0%, #e8e1d8 100%);
  color: $dark-blue;
  padding: 4rem 0 5rem;

  h2 {
    color: $dark-blue;
    font-weight: 800;
    margin-bottom: 0.75rem;
    font-size: clamp(2.1rem, 3vw, 3.2rem);
    letter-spacing: -0.06em;
  }

  p {
    color: $muted;
    line-height: 1.7;
  }

  .project-tabs {
    gap: 0.65rem;
    flex-wrap: wrap;
    justify-content: flex-start;
    margin-bottom: 2rem;

    @media (max-width: 767px) {
      justify-content: center;
    }

    .nav-item {
      margin: 0;
    }

    .nav-link {
      border-radius: 999px;
      color: $dark-blue;
      background: rgba(255, 255, 255, 0.52);
      border: 1px solid rgba(10, 37, 65, 0.12);
      padding: 0.7rem 1rem;
      font-weight: 700;
      transition: all 0.2s ease;

      &.active,
      &:hover {
        background: linear-gradient(135deg, $blue-green, $dark-blue);
        color: white;
        border-color: transparent;
        box-shadow: 0 12px 24px rgba(10, 37, 65, 0.18);
      }
    }
  }

  .project-card {
    display: flex;
    flex-direction: column;
    overflow: hidden;
    border-radius: 1.3rem;
    background: rgba(255, 255, 255, 0.8);
    border: 1px solid rgba(10, 37, 65, 0.08);
    box-shadow: 0 12px 28px rgba(10, 37, 65, 0.08);
    height: 100%;
    transition: transform 0.2s ease, box-shadow 0.2s ease;

    &:hover {
      transform: translateY(-4px);
      box-shadow: 0 18px 34px rgba(10, 37, 65, 0.12);
    }

    &__image {
      width: 100%;
      height: 185px;
      object-fit: cover;
      display: block;
      background: #dfe9ef;
    }

    &__body {
      display: flex;
      flex: 1;
      flex-direction: column;
      padding: 1rem 1rem 1.15rem;
    }

    .project-chip {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      border-radius: 999px;
      background: rgba(16, 70, 95, 0.08);
      color: $dark-blue;
      font-size: 0.68rem;
      font-weight: 700;
      padding: 0.52rem 0.8rem;
      margin-bottom: 0.8rem;
      text-transform: uppercase;
      letter-spacing: 0.08em;
      width: fit-content;
    }

    h5 {
      font-weight: 800;
      color: $dark-blue;
      font-family: $primary_font;
      margin: 0 0 0.6rem;
      font-size: clamp(1.45rem, 1.7vw, 1.9rem);
      line-height: 1.1;
      letter-spacing: -0.05em;
    }

    .project-meta {
      color: $muted;
      margin: 0;
      font-size: 0.9rem;
      line-height: 1.5;
    }

    .project-card__actions {
      display: flex;
      gap: 0.7rem;
      flex-wrap: wrap;
      margin-top: auto;
      padding-top: 1rem;
    }

    .btn-port {
      flex: 1 1 0;
      min-height: 48px;
      margin-top: auto;
      border-radius: 999px;
      background: linear-gradient(135deg, $blue-green, $dark-blue);
      color: white;
      border: none;
      padding: 0.8rem 1rem;
      font-size: 0.9rem;
      font-weight: 700;
      transition: transform 0.2s ease, box-shadow 0.2s ease;
      box-shadow: 0 10px 16px rgba(17, 97, 126, 0.12);

      &:hover {
        color: white;
        transform: translateY(-1px);
        box-shadow: 0 12px 20px rgba(17, 97, 126, 0.18);
      }
    }

    .btn-port--ghost,
    .btn-port--light {
      background: #edf3f8;
      color: $dark-blue;
      box-shadow: 0 8px 14px rgba(15, 23, 42, 0.05);

      &:hover {
        color: $dark-blue;
      }
    }
  }

  .project-modal {
    position: fixed;
    inset: 0;
    background: rgba(15, 23, 42, 0.72);
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 2rem;
    z-index: 9999;

    &__dialog {
      position: relative;
      width: 100%;
      max-width: 1200px;
      background: #eff4f8;
      border-radius: 18px;
      overflow: hidden;
      box-shadow: 0 28px 80px rgba(15, 23, 42, 0.28);
      display: grid;
      grid-template-columns: 1.05fr 1fr;
      animation: modalIn 0.2s ease;

      @media (max-width: 900px) {
        grid-template-columns: 1fr;
        max-height: calc(100vh - 1.5rem);
        overflow-y: auto;
      }
    }

    &__panel {
      &--info {
        background: rgba(234, 240, 245, 0.9);
        padding: 2.2rem 2.1rem 1.6rem;

        @media (max-width: 900px) {
          order: 2;
          padding: 2.2rem 1rem 1.25rem;
        }
      }

      &--visual {
        background: #ebeff3;
        padding: 1rem 1rem 1rem 0;

        @media (max-width: 900px) {
          order: 1;
          padding: 1rem;

          .project-modal__browser {
            display: none;
          }
        }
      }

    }

    &__info-block {
      margin-bottom: 1.5rem;

      .project-modal__label {
        display: block;
        font-size: 0.7rem;
        letter-spacing: 0.18em;
        text-transform: uppercase;
        color: rgba(61, 82, 100, 0.8);
        font-weight: 700;
        margin-bottom: 0.55rem;
      }

      h3 {
        margin: 0;
        font-size: clamp(2rem, 2.15vw, 3.1rem);
        line-height: 0.96;
        letter-spacing: -0.06em;
        color: rgba(18, 53, 82, 0.95);
        font-weight: 700;

        @media (max-width: 600px) {
          font-size: clamp(1.65rem, 7vw, 2.25rem);
          line-height: 1;
          letter-spacing: -0.04em;
        }
      }
    }

    &__meta-grid {
      display: grid;
      grid-template-columns: 1fr;
      gap: 0.9rem;
      margin-top: 0.5rem;
    }

    &__meta-item {
      background: rgba(255, 255, 255, 0.38);
      border: 1px solid rgba(128, 150, 175, 0.18);
      border-radius: 14px;
      padding: 0.9rem 1rem;
      display: flex;
      flex-direction: column;
      gap: 0.35rem;
      min-height: 96px;
      justify-content: center;

      strong {
        color: $dark-blue;
        font-size: clamp(1.5rem, 2vw, 2.5rem);
        line-height: 1.1;
        letter-spacing: -0.05em;
      }

      &--hosting {
        min-height: 96px;
      }

      &--full {
        min-height: 136px;
      }
    }

    &__label {
      display: block;
      color: rgba(61, 82, 100, 0.9);
      font-size: 0.76rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      font-weight: 800;
    }

    &__stack-icons {
      display: flex;
      flex-wrap: wrap;
      gap: 0.7rem;
      margin-top: 0.2rem;
    }

    &__tech-icon {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      width: 2.8rem;
      height: 2.8rem;
      border-radius: 12px;
      background: rgba(255, 255, 255, 0.9);
      border: 1px solid rgba(129, 155, 180, 0.2);
      box-shadow: 0 8px 18px rgba(15, 23, 42, 0.06);
      font-size: 1.35rem;

      i {
        color: $dark-blue;
      }

      .fa-wordpress { color: #0073aa; }
      .fa-php { color: #7377ad; }
      .fa-html5 { color: #e44d26; }
      .fa-css3-alt { color: #254bdd; }
      .fa-sass { color: #bf4080; }
      .fa-bootstrap { color: #563d7c; }
      .fa-js-square { color: #f0db4f; }
    }

    &__tech-logo {
      width: 1.7rem;
      height: 1.7rem;
      object-fit: contain;
      display: block;
      filter: drop-shadow(0 3px 8px rgba(15, 23, 42, 0.08));
    }

    &__browser {
      border-radius: 18px;
      overflow: hidden;
      background: rgba(19, 30, 43, 0.95);
      border: 1px solid rgba(167, 182, 199, 0.2);
      box-shadow: 0 18px 34px rgba(15, 23, 42, 0.12);
    }

    &__browser-bar {
      height: 52px;
      background: rgba(12, 21, 31, 0.9);
      border-bottom: 1px solid rgba(255, 255, 255, 0.08);
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 1rem;
      padding: 0 1rem;
    }

    &__browser-dots {
      display: flex;
      align-items: center;
      gap: 0.5rem;
      padding-left: 0.15rem;

      span {
        display: block;
        width: 12px;
        height: 12px;
        border-radius: 50%;
      }

      span:nth-child(1) {
        background: #ef4444;
      }

      span:nth-child(2) {
        background: #fbbf24;
      }

      span:nth-child(3) {
        background: #22c55e;
      }
    }

    &__visual-hero {
      position: relative;
      min-height: 360px;
      background-size: cover;
      background-position: center;
      display: block;
      box-shadow: inset 0 0 0 1px rgba(255, 255, 255, 0.04);
    }

    &__feature-card {
      margin-top: 1rem;
      background: rgba(255, 255, 255, 0.72);
      border: 1px solid rgba(128, 150, 175, 0.12);
      border-radius: 16px;
      padding: 1rem 1.1rem;

      h4 {
        margin: 0.5rem 0 0.3rem;
        font-size: clamp(1.25rem, 1.7vw, 1.8rem);
        line-height: 1.12;
        letter-spacing: -0.04em;
        color: rgba(18, 53, 82, 0.96);
        font-weight: 700;
      }

      p {
        margin: 0;
        color: rgba(41, 60, 81, 0.84);
        line-height: 1.55;
      }
    }

    &__feature-type {
      display: inline-block;
      color: $blue-green;
      text-transform: uppercase;
      letter-spacing: 0.14em;
      font-size: 0.7rem;
      font-weight: 800;
    }

    &__close {
      position: absolute;
      top: 1rem;
      right: 1rem;
      width: 2.5rem;
      height: 2.5rem;
      border: 1px solid rgba(128, 150, 175, 0.22);
      border-radius: 50%;
      background: rgba(255, 255, 255, 0.92);
      color: $dark-blue;
      font-size: 1.8rem;
      line-height: 1;
      cursor: pointer;
      box-shadow: 0 8px 18px rgba(15, 23, 42, 0.08);
      z-index: 5;
    }

    &__actions {
      display: flex;
      justify-content: flex-start;
      align-items: center;
      gap: 0.85rem;
      flex-wrap: wrap;
      margin-top: 1.5rem;

      .btn-port {
        min-width: 160px;
        padding: 0.8rem 1.3rem;
        border-radius: 999px;
        font-weight: 800;
        font-size: 0.96rem;
        letter-spacing: 0.02em;
        text-transform: none;
        border: 1px solid rgba(17, 97, 126, 0.15);
        background: linear-gradient(135deg, $blue-green 0%, $dark-blue 100%);
        color: #fff;
        box-shadow: 0 12px 22px rgba(17, 97, 126, 0.18);
        transition: transform 0.2s ease, box-shadow 0.2s ease, filter 0.2s ease;

        &:hover {
          transform: translateY(-1px);
          filter: brightness(1.03);
          box-shadow: 0 14px 26px rgba(17, 97, 126, 0.22);
          color: #fff;
        }
      }

      .btn-port--light {
        background: rgba(255, 255, 255, 0.82);
        color: $dark-blue;
        border: 1px solid rgba(128, 150, 175, 0.2);
        box-shadow: 0 8px 16px rgba(15, 23, 42, 0.06);
        font-weight: 700;

        &:hover {
          color: $dark-blue;
          background: rgba(255, 255, 255, 0.97);
          box-shadow: 0 10px 18px rgba(15, 23, 42, 0.1);
        }
      }
    }
  }
}

@keyframes modalIn {
  from {
    opacity: 0;
    transform: translateY(10px) scale(0.98);
  }
  to {
    opacity: 1;
    transform: translateY(0) scale(1);
  }
}
</style>