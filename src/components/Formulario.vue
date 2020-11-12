<template>
  <section class="container">
    <div class="text-center my-5">
      <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/98/International_Pok%C3%A9mon_logo.svg/1200px-International_Pok%C3%A9mon_logo.svg.png" alt="Pokemón">      
    </div>
    <form @submit.prevent="traerPokemon()">
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
      <img :src="imagen" alt="pokemon">
      <h3>Movimientos</h3>
      <ul>
        <li v-for="(objeto, index) in movimientos" :key="index">{{objeto.move.name}}</li>
      </ul>
      <h3>Habilidades</h3>
      <ul>
        <li v-for="(objeto, index) in habilidades" :key="index">{{objeto.ability.name}}</li>
      </ul>      
    </div>
  </section>
</template>

<script>
import axios from 'axios';

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
    //Hacer llamado a la API
    traerPokemon() {
      axios.get(`https://pokeapi.co/api/v2/pokemon/${this.nombre_pokemon}`)
      .then(result => {
        console.log(result.data)
        this.nombre_pokemon = result.data.name;
        this.imagen = result.data.sprites.front_shiny;
        this.movimientos = result.data.moves;
        this.habilidades = result.data.abilities;
      })
      .catch(error => console.log(error));
    }
  },
  created() {
    //Creo que aquí debería ir el pikachu que es el que debe venir predeterminado
    this.traerPokemon('pikachu');
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  img {
    height: 180px;
  }
  li {
    list-style: none;
  }
</style>
