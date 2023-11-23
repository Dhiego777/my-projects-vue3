<template>
  <main :class="{ 'modo-escuro': modoEscuro }">
    <div class="row">
      <div class="col-4 px-0">
        <side-bar @aoTemaAlterado="trocarTema"></side-bar>
      </div>
      <div class="col-8 px-0 conteudo">
        
      </div>
    </div>
  </main>
</template>
<script>
import SideBar from './SideBar.vue';

export default {
  name: 'TaskManager',
  components: {
    SideBar
  },
  data() {
    return {
      tasks: [],
      modoEscuro: false
    }
  },
  computed: {
    isEmptyList() {
      return this.tasks.length === 0
    }
  },
  methods: {
    saveTask(task) {
      this.tasks.push(task)
    },
    trocarTema(modoEscuro) {
      this.modoEscuro = modoEscuro;
    }
  }
}
</script>
<style scoped>

.list{
  padding: 1.25rem;
}

main {
  --bg-primario:#fff;
  --texto-primario:#000;
}

main.modo-escuro {
  --bg-primario:#2b2d42;
  --texto-primario:#ddd;
}

.conteudo {
  background-color: var(--bg-primario) ;
}
</style>
<!-- .container-fluid {
  width: 100vw;
  height: 100vh;
} -->