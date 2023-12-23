<template>
  <main :class="{ 'modo-escuro': modoEscuro }">
    <div class="row">
      <div class="col-2 px-0">
        <side-bar @aoTemaAlterado="trocarTema"></side-bar>
      </div>
      <div class="col-10 px-0 conteudo">
        <form-component class="py-1" @aoSalvarTarefa="saveTask"></form-component>
        <div class="px-3">
          <task-box class="my-3 p-3 rounded-borders shadow-sm" v-if="isEmptyList">
            Você não adicionou nenhuma tarefa
          </task-box>
          <assignment-task v-for="(task, index) in tasks" :key="index" :task="task"></assignment-task>
        </div>
      </div>
    </div>
  </main>
</template>
<script>
import SideBar from './SideBar.vue';
import FormComponent from "./FormComponent.vue";
import TaskBox from './TaskBox.vue';
import AssignmentTask from "./AssignmentTask.vue";

export default {
  name: 'TaskManager',
  components: {
    SideBar,
    FormComponent,
    TaskBox,
    AssignmentTask
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