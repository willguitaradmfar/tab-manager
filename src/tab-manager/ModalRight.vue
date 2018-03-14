<template>
<span>
  <v-navigation-drawer fixed v-model="drawerRight" right clipped app>
    <v-list dense>
      <v-list-tile @click.stop="right = !right">
        <v-list-tile-action>
          <v-icon>exit_to_app</v-icon>
        </v-list-tile-action>
        <v-list-tile-content>
          <v-list-tile-title>Open Temporary Drawer</v-list-tile-title>
        </v-list-tile-content>
      </v-list-tile>
    </v-list>
  </v-navigation-drawer>
  <v-navigation-drawer right temporary v-model="right" fixed>
  <h1>Right</h1>
  </v-navigation-drawer>
</span>
</template>

<script>
export default {
  name: "ModalRight",
  created: function() {
    this.$root.$on('clickDrawerRight', () => {
      this.drawerRight = !this.drawerRight
    });
  },
  data: () => ({
    drawerRight: true,
    right: false
  })
};
</script>