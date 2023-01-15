<template lang="pug">
v-app
  v-main(class="grey lighten-3")
    v-container(class="grey lighten-5")
      v-row(

        no-gutters
      )
        v-col(cols=3)
          v-card(
            class="pa-2"
            tile
          )
            perfil-list
        v-col(cols=9)
          v-card(
            class="pa-2"
            outlined
            tile
          )
            p a
</template>

<script>
import PerfilList from '@/components/PerfilList.vue'
export default {
  name: 'HomePage',
  components: {
    PerfilList,
  },
  data: () => ({
    n: [1,2]
  })
}
</script>