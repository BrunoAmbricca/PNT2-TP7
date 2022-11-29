<template lang="html">

  <section class="tabla-component">
    <h1>Tabla con Datos desde MockApi</h1>
    <button class="btn btn-success mr-2 mb-3" @click="getUsuarios()">GET</button>
    <div v-if="usuarios.length" class="table-responsive"> 
      <hr>
      <div class="table-responsive">
        <table class="table table-dark">
            <tr>
                <th>#</th>
                <th>Nombre</th>
                <th>Edad</th>
                <th>Email</th>
            </tr>
            <tr v-for="(usuario, index) in usuarios" :key="index">
                <td>{{ index + 1 }}</td>
                <td>{{ usuario.nombre }}</td>
                <td>{{ usuario.edad }}</td>
                <td>{{ usuario.email}}</td>
            </tr>
        </table>
      </div>
    </div>  
    <h3 v-else class="alert alert-info">No hay Usuarios en MockApi</h3>
  </section>

</template>

<script lang="js">

  export default  {
    name: 'tabla-component',
    props: [],
    mounted () {
      
    },
    data () {
      return {
        url: 'https://63643e927b209ece0f4372e0.mockapi.io/usuariosTP7',
        usuarios: []
      }
    },
    methods: {
      async getUsuarios() {
        try {
          this.axios(this.url)
          .then(response => {
            let respuesta = response.data
            this.usuarios = respuesta
          })
          .catch(error => console.error(error))
        }
        catch(error) {
           console.error('ERROR en getUsuarios', error)
        }
      }
    },
    computed: {

    }
}


</script>

<style scoped lang="css">
  .tabla-component {

  }
</style>
