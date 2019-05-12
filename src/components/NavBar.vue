<template>
  <v-toolbar dark class="primary">
    <v-toolbar-side-icon></v-toolbar-side-icon>
    <v-toolbar-title>Меню</v-toolbar-title>
    <v-spacer></v-spacer>
    <v-toolbar-items class="hidden-sm-and-down">
      <v-btn
        flat
        v-for="(item, i) in menuItem"
        :key="`menuitem${i}`"
      >
        {{ item.title}}
      </v-btn>
    </v-toolbar-items>
  </v-toolbar>
</template>

<script>

  export default {
    name: "NavBar",
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