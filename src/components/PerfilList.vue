<template lang="pug">
  v-app
    v-card
      v-subheader Elegiveis
      v-list-item( v-for="perfil in elegit" :key="perfil.avatar" )
        v-list-item-avatar
          v-img(:src="perfil.avatar")
        v-list-item-content
          v-list-item-title {{ perfil.name }}
        v-btn(
          @click="removeFromElegit"
          class="mx-1"
          fab
          dark
          small
          depressed
          color="pink lighten-3"
          )
          v-icon(dark) mdi-minus
      v-list-item(d-flex class="flex-row-reverse")
        v-btn(
          class="mx-1"
          fab
          dark
          small
          depressed
          color="pink lighten-1")
          v-icon(dark) mdi-shuffle
      v-subheader Não Elegiveis
      v-list-item( v-for="perfil in notElegit" :key="perfil.avatar" )
        v-list-item-avatar
          v-img(:src="perfil.avatar")
        v-list-item-content
          v-list-item-title {{ perfil.name }}
        v-btn(
          class="mx-1"
          fab
          dark
          small
          depressed
          color="pink lighten-2"
          )
          v-icon(dark) mdi-plus

</template>
<script>
export default {
  data: () => ({
    elegit: [
      {
        name: 'Mike Carlson',
        avatar: 'https://cdn.vuetifyjs.com/images/lists/2.jpg'
      },
      {
        name: 'Cindy Baker',
        avatar: 'https://cdn.vuetifyjs.com/images/lists/3.jpg'
      },
      {
        name: 'Ali Connors',
        avatar: 'https://cdn.vuetifyjs.com/images/lists/4.jpg'
      },
      {
        name: 'Ali Connors',
        avatar: 'https://cdn.vuetifyjs.com/images/lists/4.jpg'
      }
    ],
    notElegit: [
      {
        name: 'Mike Carlson',
        avatar: 'https://cdn.vuetifyjs.com/images/lists/2.jpg'
      }
    ]
  })
}
</script>
<style>
.v-list__tile {
  padding: 0
}
</style>