<template lang="pug">
  v-app
    v-card( max-width="500" ).mx-auto
      v-container
        v-list-item( v-for="perfil in elegit" :key="perfil.avatar" )
          v-list-item-avatar
            v-img(:src="perfil.avatar")
          v-list-item-content
            v-list-item-title {{ perfil.name }}
      v-container( class="d-flex flex-row-reverse")
        v-btn
          v-icon mdi-shuffle
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
      }
    ]
  })
}
</script>