<template>
  <NuxtLayout>
    <v-app>
      <div>
        <v-container class="grey lighten-5">
          <v-row class="mb-5" justify="center" no-gutters>
            <h1 class="text-h4">RIOS DESPOLUÍDOS PELO MUNDO</h1>
            <v-divider></v-divider>
          </v-row>
          <v-row class="mb-5" justify="center" no-gutters>
            <div class="mapa">
              <div class="buttons"> 
                <!-- <v-btn
                  size="x-small"
                  class="btn_option_1"
                  color="red"
                  icon="mdi-circle"
                >1</v-btn> -->
                
                <buttoninformation class="btn_option_a" tipo="4" ></buttoninformation>
                <buttoninformation class="btn_option_b" tipo="1" ></buttoninformation>
                <buttoninformation class="btn_option_c" tipo="2" ></buttoninformation>
                <buttoninformation class="btn_option_d" tipo="3" ></buttoninformation>
                
              </div>
              
            </div>
          </v-row>

          
        </v-container>
      </div>
    </v-app>
  </NuxtLayout>
</template>
<style >

  .mapa{
    width: 1200px;
    height: 676px;
    position: absolute;
    background-image: url("/assets/mapa.webp");
    background-position: center;
    background-size: contain;
  }

  .btn_option_a{
    position: relative;
    top: 450px;
    left: 420px;
  }
  .btn_option_b{
    position: relative;
    top: 220px;
    left: 550px;
  }
  .btn_option_c{
    position: relative;
    top: 170px;
    left: 605px;
  }
  .btn_option_d{
    position: relative;
    top: 290px;
    left: 910px;
  }
  

  .bg-main{
    background-color: #f1f2f6;
    background-image: url("/bg/bg_02.jpg");
    background-size: cover;
    background-attachment: fixed;
  }

  .logo{
    min-height: 120px;
  }

  /* nav.v-navigation-drawer .v-list-item--active{
    border-right: 2px solid red;
  } */

  .logo-title{
    font-family: "Megatron";
  }

  .menucoins{
    transform: skewX(-15deg);
  }

  .menu-tooltip{
    position: fixed;
    z-index: 99999;
    min-width: 50px;
    margin-left: 40px;
  }
</style>