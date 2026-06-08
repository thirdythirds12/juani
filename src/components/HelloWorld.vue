<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    
  </div>
  <section>
    <div class="container-fluid">
      <div class="row">
        <div class="col-md-6">test</div>
        <div class="col-md-6">test 2</div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
