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

const OtherMassivePage = r => require.ensure([], () => r(require('@/components/HelloWorld')))

export default {
  name: "App",
  components: {
    Top, Footer, ModalRight, ModalLeft
  },
  created() {
   
    this.$router.addRoutes([{
      path: '/',
      name: 'HelloWorld',
      component: OtherMassivePage
    }]);
  }
};
</script>
