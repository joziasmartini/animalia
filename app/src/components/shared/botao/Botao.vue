<template>
    <div>
        <button @click="disparaAcao()" :class="estiloDoBotao" :type="tipo">{{ rotulo }}</button>
    </div>
</template>

<script>
export default {
    props: ['tipo', 'rotulo', 'confirmacao', 'estilo'],
    methods: {
        disparaAcao() {
            if(this.confirmacao) {
                if(confirm('Confirma operação?')) {
                    this.$emit('botaoAtivado');
                }
                return;
            }
            this.$emit('botaoAtivado',)
        }
    },
    computed: {
        estiloDoBotao() {
            if(this.estilo == "padrao" || !this.estilo) return 'botao botao-padrao';
            if(this.estilo == "perigo") return 'botao botao-perigo';
        }
    }
}
</script>

<style scoped>
    .botao {
        display: inline-block;
        padding: 10px;
        border-radius: 3px;
        margin: 10px;
        font-size: 1.2em;
    }

    .botao-perigo {
        background: firebrick;
        color: white;
    }

    .botao-padrao {
        background: darkcyan;
        color: white;
    }
</style>