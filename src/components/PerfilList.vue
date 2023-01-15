<template lang="pug">
v-app
  v-card
    v-subheader Elegiveis
    v-list-item( v-for="perfil in elegit" :key="perfil.id" )
      v-list-item-avatar
        v-img(:src="perfil.avatar")
      v-list-item-content
        v-list-item-title {{ perfil.name }}
      v-btn(
        @click="removeFromElegit(perfil.id)"
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
        dark
        small
        depressed
        title
        color="pink lighten-1") Apply
    v-subheader Não Elegiveis
    v-list-item( v-for="perfil in notElegit" :key="perfil.id" )
      v-list-item-avatar
        v-img(:src="perfil.avatar")
      v-list-item-content
        v-list-item-title {{ perfil.name }}
      v-btn(
        @click="removeFromNotElegit(perfil.id)"
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
        id: 1,
        name: 'Mike Carlson',
        avatar: 'https://cdn.vuetifyjs.com/images/lists/2.jpg'
      },
      {
        id: 2,
        name: 'Cindy Baker',
        avatar: 'https://cdn.vuetifyjs.com/images/lists/3.jpg'
      },
      {
        id: 3,
        name: 'Ali Connors',
        avatar: 'https://cdn.vuetifyjs.com/images/lists/4.jpg'
      },
    ],
    notElegit: [
      {
        id: 4,
        name: 'Joerge Carldone',
        avatar: 'https://cdn.vuetifyjs.com/images/lists/1.jpg'
      }
    ]
  }),
  methods: {
    removeFromElegit(perfilId) {
      const element = this.elegit.find(element => element.id == perfilId)

      this.elegit = this.elegit.filter(e => e != element)
      this.notElegit.push(element)
    },
    removeFromNotElegit(perfilId) {
      const element = this.notElegit.find(element => element.id == perfilId)

      this.notElegit = this.notElegit.filter(e => e != element)
      this.elegit.push(element)
    }
  }
}
</script>