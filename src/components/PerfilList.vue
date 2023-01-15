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
        @click="applyClicked()"
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
  props: {
    initialEligit: {
      type: Array,
      default: () => [],
    },
    initialNotEligit: {
      type: Array,
      default: () => [],
    }
  },
  data() {
    return {
      elegit: [],
      notElegit: [],
    }
  },
  mounted(){
    this.elegit = this.initialEligit;
    this.notElegit = this.initialNotEligit;
  },
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
    },
    applyClicked() {
      if (this.elegit.length % 2 == 0) {
        this.$emit('pairs', this.makeRandomPairs())
      }
    },
    makeRandomPairs() {
      let pair = []
      let element = undefined
      let elements = this.elegit
      let allPairs = []

      while(elements.length){
        pair = []

        for(let i=0;i<2;i++){
          element = elements[Math.floor(Math.random()*elements.length)];
          pair.push(element)

          elements = elements.filter(e => e != element)
        }
        allPairs.push(pair)
      }
      return allPairs
    }
  }
}
</script>