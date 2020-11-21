<template>
  <section id="portskills" class="h-100">
    <div class="container d-flex align-items-center justify-content-center">
      <div class="row">
        <div class="col-md-12">
          <h2 v-html="data.title"></h2>
          <br>
          <p v-html="data.subtitle"></p>
        </div>
      </div>
    </div>
    <div class="container">
      <div class="row">
        <div class="col-md-12">
          <h2 v-html="data.langtoolstitle"></h2>
        </div>
      </div>
      <br>
      <ul class="nav nav-tabs" role="tablist">
        <li class="nav-item" v-for="data in data.tabstitlecontents" :key="data.tabstitlecontents">
          <a :class="data.tabtitleclass" data-toggle="tab" :href="data.tabtitlelink" role="tab">
            {{ data.tabtitle }}</a>
        </li>
      </ul><!-- Tab panes -->
      <div class="tab-content">
        <div v-for="data in data.tabscontent" :class="data.tabcontentclass" :id="data.tabcontentid" role="tabpanel" :key="data.tabscontents">
          <ul>
            <li v-for="data in data.contents" :key="data.contents">
              <i :class="data.fontawesomeclass"></i> <h5 v-html="data.content"></h5>
              <div class="progress">
                <div class="progress-bar progress-bar-success" :id="data.progressbarid">{{data.percentagecontent}}</div>
              </div>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
    export default {
        name: "portskills",
        props: ["data"]
    };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
    @import "../assets/styles/_website.scss";
    #portskills {
        background-color: white;
        .container {
            padding-top: 2%;
        }
        h2 {
            font-weight: bold;
            color: $dark-blue;
            font-family: $primary_font;
        }
        .nav-tabs {
            border-bottom: 1px solid $light-green;
            li {
                width: 25%;
            @media (max-width: 424px) {
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
                    .progress {
                        background-color: $blue-green;
                        .progress-bar {
                            animation-name: animateBar;
                            animation-iteration-count: 1;
                            animation-timing-function: ease-in;
                            animation-duration: 1s;
                            color: $dirty-white;
                            background-color: $dark-blue;
                            font-weight: bold;
                            font-size: 1.1rem;
                            line-height: 1.1rem;
                        }
                    }
                    @keyframes animateBar {
                        0% {
                            transform: translateX(-100%);
                        }
                        100% {
                            transform: translateX(0);
                        }
                    }
                    i {
                        margin-bottom: 1rem;
                        font-size: 2rem;
                    }
                    h5 {
                        font-size: 1.5rem;
                        font-family: $primary_font;
                    }
                }
            }
        }
        #fifty {
            width: 50%;
        }
        #sixty-five {
            width: 65%;
        }
        #eighty {
            width: 80%;
        }
        #seventy {
            width: 70%;
        }
        #ninety {
            width: 90%;
        }
    }
</style>