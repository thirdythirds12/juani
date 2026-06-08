<template>
  <section id="projects" class="h-100">
    <div class="container d-flex align-items-center justify-content-center">
      <div class="row">
        <div class="col-md-12">
          <h2 v-html="data.title" data-aos="fade-in" data-aos-duration="1000"></h2>
          <br />
          <p v-html="data.subtitle" data-aos="fade-in" data-aos-duration="1000"></p>
        </div>
      </div>
    </div>
    <div class="container">
      <ul class="nav nav-tabs" role="tablist" data-aos="fade-in" data-aos-duration="1000">
        <li
          class="nav-item"
          v-for="data in data.tabstitlecontents"
          :key="data.tabstitlecontents"
        >
          <a
            :class="data.tabtitleclass"
            data-toggle="tab"
            :href="data.tabtitlelink"
            role="tab"
          >
            {{ data.tabtitle }}</a
          >
        </li>
      </ul>
      <!-- Tab panes -->
      <div class="tab-content">
        <div
          v-for="data in data.tabscontent"
          :class="data.tabcontentclass"
          :id="data.tabcontentid"
          role="tabpanel"
          :key="data.tabscontents"
        >
          <div class="row">
            <div
              class="col-md-4 card-container"
              v-for="data in data.contents"
              :key="data.contents"
              
            >
              <div class="card" data-aos="flip-left" data-aos-duration="1000">
                <img
                  class="card-img-top"
                  alt="Card image cap"
                  :src="data.projectimg"
                />
                <div class="card-body">
                  <h5 class="card-title" v-html="data.projecttitle"></h5>
                  <p class="card-text" v-html="data.projecttype"></p>
                  <p class="card-text" v-html="data.projectyear"></p>
                  <p class="card-text" v-html="data.projectposition"></p>
                  <a
                    :href="data.projectlink"
                    target="_blank"
                    class="btn btn-port"
                    >Visit Website</a
                  >
                </div>
              </div>
            </div>
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
#projects {
  background-color: white;
  .container {
    padding-top: 2%;
  }
  h2 {
    color: $dark-blue;
    @media only screen and (max-width: 424px) {
      font-size: 7.5vw;
    }
  }
  p {
    color: $dark-blue;
  }
  .nav-tabs {
    border-bottom: 1px solid $light-green;
    li {
      width: 33.3%;
      @media (max-width: 568px) {
        width: 100%;
      }
      a {
        color: $dark-blue;
        font-weight: bold;
      }
      .active {
        font-weight: bold;
        color: white;
        background-color: $blue-green;
        border-color: $blue-green $blue-green #fff;
      }
    }
  }
  .tab-content {
    ul {
      list-style: none;
      padding: 1% 0;
      li {
        padding: 1%;
        i {
          margin-bottom: 1rem;
          font-size: 2rem;
        }
        h5 {
          font-size: 1.5rem;
          font-family: $primary_font;
          font-weight: bold;
          color: $dark-blue;
        }
      }
    }
  }
  .card-container {
    padding: 2%;
    position: relative;
    top: 0;
    transition: top 0.5s;
    &:hover {
      top: -10px;
    }
    .card {
      border-bottom: 1px solid $blue-green;
      &:hover {
        border-bottom: 1px solid $dark-blue;
      }
      p {
        font-family: $primary_font;
        color: $dark-blue;
        &:nth-child(-n + 3) {
          margin: 0;
        }
      }
      h5 {
        font-weight: bold;
        color: $dark-blue;
        font-family: $primary_font;
      }
      .btn-port {
        cursor: pointer;
        outline: none;
        color: #fff;
        background-color: $blue-green;
        box-shadow: 0 6px $dark-blue;
        border-radius: 1%;
        &:hover {
          background-color: $blue-green;
        }
        &:active {
          background-color: $blue-green;
          box-shadow:0 2px $dark-blue;
          transform: translateY(4px);
        }
      }
    }
  }
}
</style>