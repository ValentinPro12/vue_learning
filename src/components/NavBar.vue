<template>
  <v-app>
    <v-navigation-drawer
      absolute
      temporary
      v-model="drawer">
      <v-list>
        <v-list-tile
          v-for="(item, i) in menuItem"
          :key="`navdrawer${i}`"
        >
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title"></v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar dark class="primary">
      <v-toolbar-side-icon
      @click.stop="drawer = !drawer"
      ></v-toolbar-side-icon>
      <v-toolbar-title>Меню</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items class="hidden-sm-and-down">
        <v-btn
          flat
          v-for="(item, i) in menuItem"
          :key="`menuItem${i}`"
        >
          {{ item.title}}
        </v-btn>
      </v-toolbar-items>
    </v-toolbar>
  </v-app>
</template>

<script>

  export default {
    name: "NavBar",
    data() {
      return {
        drawer: false
      }
    },
    computed: {
      menuItem() {
        return [
          {
            title: 'Главная',
          },
          {
            title: 'Примены работ',
          },
          {
            title: 'Обратная связь',
            route: '/w'
          }
        ]
      }
    }
  }
</script>

<style scoped>

</style>