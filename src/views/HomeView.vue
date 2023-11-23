<template>
  <div class="container-fluid background-home-view">
    <div class="row">
      <div class="col-md-6">
        <div class="card">
          <img src="../assets/cronometro.jpg" class="card-img-top" alt="...">
          <div class="card-body">
            <h5 class="card-title text-center">Gerenciador de tarefas</h5>
            <p class="card-text">Cria uma lista de tarefes, onde é salvo o tempo que foi feito e a descrição.
              Contém um contador de tempo com ações de play e pause.</p>
            <router-link class="d-grid gap-2" to="/taskManager">
              <button class="btn btn-primary" type="button">Acessar projeto</button>
            </router-link>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
  
<script>

export default {
  name: 'HomeView',
}
</script>

<style scoped>
.background-home-view {
  width: 100vw;
  height: 100vh;
  background-color: rgb(212, 212, 212);
}
</style>
