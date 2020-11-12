<template>
  <section class="container">
    <div class="text-center my-5">
      <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/98/International_Pok%C3%A9mon_logo.svg/1200px-International_Pok%C3%A9mon_logo.svg.png" alt="Pokemón">      
    </div>
    <form @submit.prevent="traerpokemon()">
      <div class="form-group">
        <label for="formGroupExampleInput">Ingresa el nombre de tu pokemón:</label>
        <input type="text" class="form-control" id="formGroupExampleInput" placeholder="Bulbasaur" v-model="nombre_pokemon">
      </div>
      <div class="text-right">
        <button type="submit" class="btn btn-danger">Buscar</button>        
      </div>
    </form>
    <!-- Mostrar nombre, imagen, etc. -->
    <div class="text-center my-5">
      <img src="" alt="">
      <h3>Movimientos</h3>
      <ul>
        <li></li>
      </ul>
      <h3>Habilidades</h3>
      <ul>
        <li></li>
      </ul>      
    </div>
  </section>
</template>

<script>
export default {
  name: 'Formulario',
  data() {
    return {
      nombre_pokemon: '',
      imagen: '',
      movimientos: [],
      habilidades: [],
    }
  },
  methods: {
    traerpokemon() {
      // hacer el llamado a la API
    }
  },
  created() {
    //Creo que aquí debería ir el pikachu que es el que debe venir predeterminado
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  img {
    height: 180px;
  }
  li {
    list-style-type: none;
  }
</style>
