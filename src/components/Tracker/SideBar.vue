<template>
    <div class="container px-0 mx-0">
        <h1>
            <img src="../../assets/logo.png" alt="Logo alura">
        </h1>
        <button class="button" @click="alterarTema">
            {{ textoBotao }}
        </button>
    </div>
    <!-- <div>
    </div> -->
</template>
<script>

export default {
    name: 'SideBar',
    emits: ['aoTemaAlterado'],
    data(){
        return {
            modoEscuro: false
        }
    },
    computed: {
        textoBotao() {
            if(this.modoEscuro) {
                return 'Desativar modo escuro'
            }
            return 'Ativar modo escuro'
        }
    },
    methods: {
        alterarTema() {
            this.modoEscuro = !this.modoEscuro;
            this.$emit("aoTemaAlterado", this.modoEscuro);
        }
    }
}
</script>
<style scoped>

</style>

