<template >
    <div class="usuario-detalhe">
        <h3>Usuário Detalhe</h3>
        <hr>
        <p><strong>Código:</strong> {{ id }}</p>
        <!-- :to="`/usuario/${id}/editar`" -->
        <router-link tag="button" primario :to="{ name: 'editarUsuario', params: { id }, 
            query: { completo: false, lingua: 'pt'},
            hash: '#rodape' }">
        <!--:to="`/usuario/${$route.params.id}/editar`"  Uma forma de interpolar o id -->
            Editar
        </router-link>
    </div>
</template>

<script>
export default {
    props: ['id'],
    beforeRouteEnter (to, from, next) {
        console.log('dentro do componente usuario detalhe')
        // next(vm => {
        //     console.log(vm.id)
        // })

        const autenticado = true
        autenticado ? next() : next(false)
    }
  
  // data() {
  //   return {
  //     id: this.$route.params.id
  //   }
  // },
  // watch: {
  //   // eslint-disable-next-line no-unused-vars
  //   $route(to, from) {
  //     this.id = to.params.id
  //   }
  // },
}
</script>

<style>

</style>