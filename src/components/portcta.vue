<template>
    <section id="contact-me">
        <div class="container py-3">
            <div class="row">
                <div class="col-md-12">
                    <h2 v-html="data.title" ></h2>
                </div>
            </div>
            <br>
            <div class="row">
                <div class="col-md-3 col-sm-6" v-for="data in data.contents"
                :key="data.contents">
                    <i :class="data.fontawesomeclass" ></i><br>
                    <a :href="data.contactlink" > {{data.contactcontent}}</a>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
    export default {
        name: "portcta",
        props: ["data"],
        components: {},
    }
</script>

<style lang="scss">
    @import "../assets/styles/_website.scss";
    #contact-me {
        background-color: $blue-green;
        color: white;
        .col-sm-6 {
            a {
                color: white;
            }
            i {
                font-size: 2rem;
            }
        }
    }
</style>