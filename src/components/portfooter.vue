<template>
  <section id="portfooter">
    <div class="container-fluid">
      <div class="row">
        <div class="col-md-12 text-center">
           <p>{{footerContent.text}}</p>  
        </div>
      </div>
    </div>
  </section>
</template>

<script>
    export default {
        name: 'portfooter',
        props: ['footer-content']
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
    @import "../assets/styles/_website.scss";
</style>