<template>
  <section class="skills-section">
    <!-- <div class="container py-5" id="about-me">
      <div class="row mb-4">
        <div class="col-lg-8">
          <h2 data-aos="fade-in" data-aos-duration="1000" v-html="data.title"></h2>
          <p class="lead-text" data-aos="fade-in" data-aos-duration="1000" v-html="data.subtitle"></p>
        </div>
      </div>
    </div> -->

    <div class="container py-5">
      <div class="row mb-3">
        <div class="col-md-12">
          <h2 data-aos="fade-in" data-aos-duration="1000" v-html="data.langtoolstitle" id="skills"></h2>
          <p class="lead-text" data-aos="fade-in" data-aos-duration="1000">I combine clean UI, modern front-end development, and reliable delivery to create websites that feel polished and perform well.</p>
        </div>
      </div>


      <ul class="nav nav-pills skill-tabs" role="tablist" data-aos="fade-in" data-aos-duration="1000">
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
              class="col-md-6 col-xl-4 mb-4"
              v-for="(item, index) in group.contents"
              :key="item.content + index"
              data-aos="fade-up"
              data-aos-duration="900"
            >
              <div class="skill-card">
                <div class="skill-card__top">
                  <img
                    v-if="item.imgsrc"
                    :src="item.imgsrc"
                    :alt="item.content"
                    class="skill-logo"
                  />
                  <span v-else class="skill-icon" :class="item.fontawesomeclass"></span>
                  <span class="skill-level">{{ item.percentagecontent }}</span>
                </div>
                <h5 v-html="item.content"></h5>
                <div class="progress" aria-label="Skill level">
                  <div class="progress-bar" :id="item.progressbarid" :style="{ width: item.percentagecontent }"></div>
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
  name: "portskills",
  props: ["data"],
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
@import "../assets/styles/_website.scss";

.skills-section {
  background:
    linear-gradient(180deg, rgba(245, 248, 252, 0.98), rgba(255, 255, 255, 1));
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

  .mini-card {
    background: white;
    border: 1px solid #e4ebf3;
    border-radius: 16px;
    padding: 1rem;
    box-shadow: 0 10px 24px rgba(15, 23, 42, 0.06);

    strong {
      display: block;
      color: $dark-blue;
      font-size: 1.02rem;
      margin-bottom: 0.2rem;
    }

    span {
      color: #48607a;
      font-size: 0.95rem;
    }
  }

  .skill-tabs {
    display: flex;
    align-items: center;
    justify-content: flex-start;
    gap: 0.75rem;
    border-bottom: none;
    flex-wrap: wrap;
    margin-bottom: 1rem;
    padding-left: 0;
    list-style: none;

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
      white-space: nowrap;
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

  .skill-card {
    background: white;
    border: 1px solid #e4ebf3;
    border-radius: 18px;
    padding: 1rem;
    height: 100%;
    box-shadow: 0 14px 30px rgba(15, 23, 42, 0.08);
    transition: transform 0.2s ease, box-shadow 0.2s ease;

    &:hover {
      transform: translateY(-4px);
      box-shadow: 0 18px 32px rgba(15, 23, 42, 0.12);
    }

    &__top {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 0.75rem;
      margin-bottom: 0.75rem;
    }

    .skill-logo {
      width: 2.2rem;
      height: 2.2rem;
      object-fit: contain;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      border-radius: 10px;
      background: rgba(17, 97, 126, 0.03);
      padding: 0.35rem;
    }

    .skill-icon {
      font-size: 1.4rem;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      width: 2.5rem;
      height: 2.5rem;
      border-radius: 12px;
      background: rgba(17, 97, 126, 0.08);
    }

    .skill-level {
      color: $blue-green;
      font-weight: 700;
      font-size: 0.95rem;
    }

    h5 {
      font-size: 1.05rem;
      font-weight: 700;
      color: $dark-blue;
      margin-bottom: 0.75rem;
      min-height: 3rem;
    }

    .progress {
      height: 0.5rem;
      border-radius: 999px;
      background-color: #edf3f8;
      overflow: hidden;

      .progress-bar {
        border-radius: 999px;
        background: linear-gradient(135deg, $blue-green, $dark-blue);
        animation: animateBar 0.6s ease both;
      }
    }
  }

  .sass-c { color: #bf4080; }
  .vue-c { color: #4fc08d; }
  .ng-c { color: #dd0031; }
  .js-c { color: #c7c702; }
  .boots-c { color: #563d7c; }
  .html-c { color: #e44d26; }
  .css-c { color: #254bdd; }
  .wp-c { color: #0073aa; }
  .php-c { color: #7377ad; }
  .git-c { color: #eb4d28; }
  .npm-c { color: #cb3837; }
  .server-c { color: #007bff; }
  .default-c { color: #212529; }
  .office-c { color: #1e7e34; }
  .trouble-c { color: #dc3545; }
}

@keyframes animateBar {
  from { transform: translateX(-8%); opacity: 0.8; }
  to { transform: translateX(0); opacity: 1; }
}
</style>