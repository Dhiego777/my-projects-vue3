<template>
	<div class="formulario shadow">
		<div class="row m-3">
			<div class="col-9">
				<input type="text" class="form-control" placeholder="Qual tarefa você deseja iniciar?" v-model="description" />
			</div>
			<div class="col">
				<ElectronicTaskTimer @aoTemporizadorFinalizado="stopTask"/>
			</div>
		</div>
	</div>
</template>
<script>
import ElectronicTaskTimer from "./ElectronicTaskTimer.vue";

export default {
	emits: ['aoSalvarTarefa'],
	components:{
		ElectronicTaskTimer
	},
	data() {
		return {
			description: ''
		}
	},
	methods: {
		stopTask(timeInSeconds) {
      this.$emit('aoSalvarTarefa', {
        durationInSeconds: timeInSeconds,
        description: this.description
      })
      this.description = '';
    }
	}
}
</script>
<style>
.formulario {
	color: var(--texto-primario);
	background-color: var(--bg-primario);
}
</style>