<template>
<span>
  <v-navigation-drawer fixed v-model="drawer" app>
      <v-list dense>
        <v-list-tile @click.stop="left = !left">
          <v-list-tile-action>      
            <v-icon>exit_to_app</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
           
            <hr/>
            <ul>
              <li>
                <a v-for="m in menu" :key="m.hash" :href="'#' + m.path" >{{m.name}}</a>
              </li>
            </ul>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-navigation-drawer temporary v-model="left" fixed>
    </v-navigation-drawer>
</span>
</template>

<script>
import menu from "../data/menu";

export default {
  name: "ModalLeft",
  created: function() {
    this.$root.$on('clickDrawer', () => {
      this.drawer = !this.drawer
    });
  },
  data: () => ({
    drawer: true,
    left: false,
    menu
  })
};
</script>