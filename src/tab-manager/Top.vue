<template>
  <v-toolbar color="blue-grey" dark fixed app clipped-right>
      <v-toolbar-side-icon @click.stop="clickDrawer"></v-toolbar-side-icon>
      <v-toolbar-title>ERP teste</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-side-icon @click.stop="clickDrawerRight"></v-toolbar-side-icon>
    </v-toolbar>
</template>

<script>
export default {
  name : 'Top',
  methods:{
    clickDrawer(){
      this.$root.$emit('clickDrawer')
    },
    clickDrawerRight(){
      this.$root.$emit('clickDrawerRight')
    }
  }
}
</script>
