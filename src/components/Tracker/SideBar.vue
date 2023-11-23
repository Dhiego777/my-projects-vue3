<template>
    <div class="container px-0 mx-0">
        <h1>
            <img src="../../assets/logo.png" alt="Logo alura">
        </h1>
        <button class="button" @click="alterarTema">
            {{ textoBotao }}
        </button>
    </div>
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
div .container {
    padding: 1rem;
    background: #0d3b66;
    width: 100%;
    height: 100vh;
    text-align: center;
}
@media only screen and (max-width: 768px) {
    div .container {
        padding: 2.5rem;
        height: auto;
    }
}
</style>

