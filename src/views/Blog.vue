<template>
  <div v-for="item in arrayBlog" :key="item.id">
    <!--Si hay que meter javascript dinámico con comillas invertidas ademas de comillas dobles normales en el to-->
    <router-link :to="`/blog/${item.id}`">
      {{item.title}}
    </router-link>
  </div>
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
      arrayBlog: []
    }
  },
  methods:{
    async consumirApi(){
      try {
        const data = await fetch('https://jsonplaceholder.typicode.com/posts')
        const array = await data.json()
        this.arrayBlog= array
        console.log(array)
      }catch (e) {
        console.log(error)
      }

    }
    //Ver ciclo de vida en vue, este método se llama antes de que se pinte la pagina, metodo de vue.
  },created() {
    this.consumirApi()
  }
}
</script>

<style scoped>

</style>