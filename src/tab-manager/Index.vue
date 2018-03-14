<template>
<v-app id="inspire">
    <ModalRight/>
    <Top/>
    <ModalLeft/>
    <v-content>
      <router-view/>
    </v-content>    
    <Footer/>
  </v-app>
</template>

<script>
import Top from "./Top";
import Footer from './Footer'
import ModalRight from './ModalRight'
import ModalLeft from './ModalLeft'

export default {
  name: "App",
  components: {
    Top, Footer, ModalRight, ModalLeft
  }
};
</script>

<style>

</style>
