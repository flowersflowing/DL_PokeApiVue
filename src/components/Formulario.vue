<template>
  <section class="container">
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/98/International_Pok%C3%A9mon_logo.svg/1200px-International_Pok%C3%A9mon_logo.svg.png" alt="Pokemón">
    <form @submit.prevent="">
      <div class="form-group">
        <label for="formGroupExampleInput">Ingresa el nombre de tu pokemón</label>
        <input type="text" class="form-control" id="formGroupExampleInput" placeholder="Bulbasaur" v-model="nombre_pokemon">
      </div>
      <button type="submit" class="btn btn-danger">Buscar</button>
    </form>
    <!-- Mostrar nombre, imagen, etc. -->
  </section>
</template>

<script>
export default {
  name: 'Formulario',
  // data() {
  //   return {
  //     nombre_pokemon
  //   }
  // }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  img {
    height: 180px;
    padding: 3em;
  }
</style>
