<template>
  <div class="orgs">
    <h1>{{ msg }}</h1>
    <ul>
      <li v-for="org in orgs" :key="org.id">{{org.name}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Orgs',
  props: {
    msg: String,
    orgs: []
  },
  mounted () {
  this.$http
      .get('http://localhost:8000/orgs/')
      .then(response => (this.orgs = response.data))
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
