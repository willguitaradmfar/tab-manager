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
import Footer from "./Footer";
import ModalRight from "./ModalRight";
import ModalLeft from "./ModalLeft";

import menu from "../data/menu";

export default {
  name: "App",
  components: {
    Top,
    Footer,
    ModalRight,
    ModalLeft
  },
  created() {
    for (let m of menu) {
      this.$router.addRoutes([
        {
          path: m.path,
          name: m.name,
          component: resolve => {
            const script = document.createElement("script");
            const link = document.createElement("link");
            link.rel = "stylesheet";
            script.src = m.js;
            link.href = m.css;
            const head = document.querySelector("head");
            head.appendChild(script);
            head.appendChild(link);
            script.onload = function() {
              return require.ensure([], () =>
                resolve(__webpack_require__(m.hash))
              );
            };
          }
        }
      ]);
    }
  }
};
</script>
