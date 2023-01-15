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
            outlined
            tile
          )
            perfil-list(:initialEligit="elegite()" :initialNotEligit="notElegit()" @pairs="parsePairs")
        v-col(cols=9)
          v-card(
            class="pa-2"
            outlined
            tile
          )
            match-list(:value='matches')
</template>

<script>
import PerfilList from '@/components/PerfilList.vue'
import MatchList from '@/components/MatchList.vue';
import * as Users from '@/mockedUsers.json';

export default {
  name: 'HomePage',
  components: {
    PerfilList,
    MatchList
  },
  data() {
    return {
      matches: [],
    }
  },
  methods: {
    elegite(){
      return Users.users.filter(u => u.id % 2 == 0)
    },
    notElegit(){
      return Users.users.filter(u => u.id % 2 != 0)
    },
    parsePairs(pairs) {
      let i = 1
      let pair = undefined
      let allPairs = []

      for (const element of pairs){
        pair = {
          id: i,
          first: element[0],
          second: element[1],
        }
        allPairs.push(pair)
        i++
      }
      this.matches = allPairs
    },
  },
}
</script>