<template>
  <Titulo texto="Artículo"/>
  <h3>{{this.articulo.title}}</h3>
  <p>{{this.articulo.id}}--{{this.articulo.body}}</p>

</template>

<script>
import Titulo from "../components/Titulo";
export default {
  name: "Articulo",
  components: {
    Titulo
  },
  data() {
    return {
      articulo:{}
    }
  },
  methods: {
    async consumirApi() {
      try {
        const data = await fetch(`https://jsonplaceholder.typicode.com/posts/${this.$route.params.id}`)
        const objeto = await data.json()
        this.articulo = objeto
        console.log(objeto)
      } catch (e) {
        console.log(e)
      }

    }
  }
  , created() {
    this.consumirApi()
  }
}
</script>

<style scoped>

</style>