<template lang="pug">
v-app
  v-list
    v-list-item(v-for="match in matches")
      v-list-item-content.mr-1
        v-list-item-title(class="text-right") {{match.first.name}}
      v-list-item-avatar.mr-1
        v-img(:src="match.first.avatar")
      v-icon mdi-plus
      v-list-item-avatar.ml-1
        v-img(:src="match.second.avatar")
      v-list-item-content.ml-1
        v-list-item-title {{match.second.name}}
</template>
<script>
export default {
  props: {
    value: {
      type: Array,
      default: () => [],
    }
  },
  data: () => ({
    matches: []
  }),
  mounted() {
    this.matches = this.value
  }
}
</script>