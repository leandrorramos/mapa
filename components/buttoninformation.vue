<template>
    <div>
        <v-btn
            v-bind="props"
            color="red"
            icon="mdi-circle"
            @click="openDialog()"
        >{{ tipo }}</v-btn>
        
        <v-dialog
            v-model="showDialog"
            width="auto"
            >
            <v-card style="min-width: 900px; max-width: 1080px;">
                <v-card-title class="bg-blue-darken-2">
                    <div class="d-flex align-center justify-space-between">
                        <h4 class="text-caption text-md-overline font-weight-bold"><v-icon color="blue" icon="mdi-information" small></v-icon> Informações sobre o rio</h4>
                        <v-btn variant="text" size="small" color="white" @click="closeDialog()">
                            <v-icon>mdi-close</v-icon>
                        </v-btn>
                    </div>
                </v-card-title>

                <v-card-text class="align-center justify-center text-center">
                    <div class="mb-3"> 
                        <p class="text-h4 text-center font-weight-bold" style="min-width: 200px;"> {{ info[tipo].title }}</p>
                    </div>
                    <div class="d-flex align-center justify-center">
                        <div class="align-center justify-center mr-3"> 
                            <img :src="info[tipo].img_antes" width="500px" />
                            <p class="text-caption text-center">Antes</p>
                        </div>
                        <div class="text-center ml-3">
                            <img :src="info[tipo].img_depois" width="500px" />
                            <p class="text-caption text-center">Depois</p>
                        </div>
                    </div>
                    <div class="text-content">
                        <div class="text-body-2 text-justify mt-5" v-html="info[tipo].description"></div>
                    </div>
                </v-card-text>

                <v-card-actions>
                    
                    <!-- <v-btn
                        class="text-caption text-md-overline"
                        text
                        @click="closeDialog()"
                    >
                        FECHAR
                    </v-btn> -->
                </v-card-actions>
            </v-card>
        </v-dialog>
    </div>
</template>

<script setup lang="ts">
    const info = [
        {
            title:"",
            img_antes:"",
            img_depois:"",
            description:`<p></p>`
        },
        {
            title:"Rio Tâmisa, Londres", 
            img_antes:"assets/rios/tamisa_antes.jpg",
            img_depois:"assets/rios/tamisa_depois.jpg",
            description:`<p>Em 1610 a água do rio já não era mais considerada potável. No entanto, o auge da sua poluição aconteceu no século XIX, em 1858, quando recebeu o nome de Grande Fedor.</p>
                         <p>Além do mau cheiro, as epidemias de cólera que assolaram a Inglaterra nas décadas de 1850 a 1860 foram fundamentais para que o governo investisse na construção de um sistema de coleta de esgoto na cidade.</p>
                         <p>Ao todo, foram quase 150 anos de investimentos na despoluição das águas do rio que corta Londres. O trabalho, no entanto, se mantém ininterrupto. Todas as semanas, são retiradas em média 30 toneladas de 
                         lixo do rio, por dois barcos que percorrem o Tâmisa realizando a sua limpeza.</p>`
        },
        {
            title:"Rio Sena, Paris", 
            img_antes:"assets/rios/sena_antes.jpg",
            img_depois:"assets/rios/sena_depois.jpg",
            description:`<p>O rio Sena, já foi considerado “morto” – a vida não se desenvolvia mais em suas águas. Isso aconteceu porque ele recebia grande quantidade de poluição vinda das indústrias que
                         se instalaram nos arredores durante o início da primeira Revolução Industrial. Além disso, o esgoto era descartado diretamente nas suas águas.</p>
                         <p>Na década de 1960, os franceses decidiram investir em sua revitalização, com a construção de estações de tratamento de esgoto e projetos de recuperação do ecossistema local.</p>
                         <p>Hoje, o Sena, além de servir de cartão-postal para a capital francesa, conta com 30 espécies de peixes e faz parte do rol de casos de sucesso de rios despoluídos pelo mundo.</p>
                         <p>O cuidado, no entanto, não pode parar. O governo mantém foco na qualidade das águas, com a criação de leis que multam empresas que despejam sujeira no rio. </p>`
        },
        {
            title:"Rio Cheonggyecheon, Seul", 
            img_antes:"assets/rios/seul_antes.jpg",
            img_depois:"assets/rios/seul_depois.jpg",
            description:`<p>Em 1958, a cidade cobriu o rio, para dar lugar a uma autoestrada principal elevada. Em 2003, o rio, que se encontrava poluído desde 1940, por ter se tornado depósito de lixo e esgoto da região, foi o objeto 
                         central de um projeto do prefeito da cidade. A ideia era humanizar a cidade, com a despoluição do rio e a construção de parques às suas margens.</p>
                         <p>Foram necessários apenas quatro anos para a limpeza total do Cheonggyecheon. Para isso, a prefeitura de Seul contou com a integração de inúmeras organizações, que ajudaram no bom andamento do projeto.</p>
                         <p>Como resultado, não somente toda a água do rio foi despoluída, como ampliou-se os espaços verdes no entorno. Com isso, a cidade ficou mais agradável e convidativa para toda a população, resultando em qualidade de vida.</p>`
        },
        {
            title:"Rio Jundiaí, São Paulo", 
            img_antes:"assets/rios/jundiai_antes.jpg",
            img_depois:"assets/rios/jundiai_depois.jpg",
            description:`<p>No Brasil também podemos encontrar casos de sucesso de rios despoluídos, como a história do Jundiaí, no interior paulista, que passa por seis cidades.</p>
                         <p>O rio já esteve na lista de um dos mais poluídos de São Paulo. Isso porque ele banha uma das áreas mais industrializadas do estado, por onde eram despejados 
                         inúmeros resíduos poluentes. Antes da despoluição, as águas do rio eram pretas como carvão e exalavam um odor muito forte.</p>
                         <p>Em 30 anos foram construídas estações de tratamento de esgoto nas cidades ao redor do seu leito. O trabalho de fiscalização também ganhou intensidade e houve
                          um esforço de preservação das matas às margens do rio. Com o empenho, o rio, que era considerado morto, passou a ter vida novamente. Hoje, o rio Jundiaí, tem 
                          peixes e água que pode ser usada para abastecimento de mais de duzentas mil pessoas.</p>`
        }
    ]

        
    const props = defineProps({        
        tipo: {
            type: String
        }
    })
    
    //dialog resources
    const showDialog = ref(false);
    const showLoading = ref(false);

    const openDialog = () => {
        showDialog.value = true;
    }

    const closeDialog = () => {
        showDialog.value = false;
        showLoading.value = false;
    }

</script>

<style >
.text-body-2 > p{
    margin: 10px 10px !important;
}
.details  .info{
    text-align: left;
    position: absolute;
    background: rgba(255, 243, 205, 0.90);
    left:0;
    bottom: 10%;
    z-index: 50;
    border: 2px solid #ddd;
    border-radius: 15px 0;
    padding: 15px;
    width: 100%;
    min-height: 50%;
    max-height: 100%;
    overflow-y: auto;
}
.info i.close{
    position: absolute;
    right: 2%;
    top: 2%;
}
</style>