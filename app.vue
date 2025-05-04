<template>
  <NuxtLayout>
    <v-app>
      <div class="content">
          <v-row class="mb-1" justify="center" no-gutters>
            <h1 class="text-h4">RIOS DESPOLUÍDOS PELO MUNDO</h1>
            <v-divider></v-divider>
          </v-row>
          <v-row class="mb-1" justify="center" no-gutters>
            <div class="mapa">
              <div class="buttons"> 

                <buttoninformation class="btn_option_a" tipo="4" ></buttoninformation>
                <buttoninformation class="btn_option_b" tipo="1" ></buttoninformation>
                <buttoninformation class="btn_option_c" tipo="2" ></buttoninformation>
                <buttoninformation class="btn_option_d" tipo="3" ></buttoninformation>
                
              </div>
              
            </div>
          </v-row>
      </div>
    </v-app>
  </NuxtLayout>
</template>
<style >
  .content{
    width: 1080px;
    height: 100%;
    position: absolute;
    overflow: hidden;
    margin-top: 10px;
  }
  .mapa{
    width: 1080px;
    height: 700px;
    position: absolute;
    background-image: url("/assets/mapa.jpg");
    background-position: center;
    background-size: contain;
  }

  .btn_option_a{
    position: relative;
    top: 445px;
    left: 355px;
  }
  .btn_option_b{
    position: relative;
    top: 135px;
    left: 500px;
  }
  .btn_option_c{
    position: relative;
    top: 125px;
    left: 535px;
  }
  .btn_option_d{
    position: relative;
    top: 125px;
    left: 915px;
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