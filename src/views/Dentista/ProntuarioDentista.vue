<template>
    <div class="container">
        <SideBar/> 
        <div class="screenContainer">

                <div v-if="frenteActive">
                    <Odontograma/>
                </div>
                <div v-if="!frenteActive">
                    <VersoDentista/>
                </div>

        </div>
    </div>
</template>

<script>
import SideBar from '../../components/SideBarProntuario.vue';
import Odontograma from '../../components/OdontogramaComponent.vue';
import VersoDentista from '../../components/VersoDentista.vue';
import { mapState } from 'vuex';


export default {
    name: "ProntuarioDentista",
    components: {
        SideBar,
        Odontograma,
        VersoDentista
    },
    computed: {
        ...mapState(['frenteActive']),
    }
};
</script>

<style scoped>
/* Certifique-se de que o body e o html ocupam 100% da altura */
html, body {
    margin: 0;
    padding: 0;
    height: 100%;
}

.container {
    display: flex;
    height: 100vh; /* Certifique-se de que ocupa a altura total da tela */
}

.screenContainer {
    width: calc(100% - 135px); /* Compensa a largura da sidebar */
    height: 100vh; /* Ocupa a altura total da tela */
    background-color: rgb(255, 255, 255);
    margin-left: 135px; /* Garante que a screenContainer comece após a sidebar */
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>
