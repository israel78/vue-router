<template>
  <div class="about">
    <Titulo texto="Este es el about"></Titulo>
  </div>
</template>
<script>
  // @ is an alias to /src
  import Titulo from "../components/Titulo";
  export default {
  name: 'Home',
  components: {
  Titulo
}
}
</script>
