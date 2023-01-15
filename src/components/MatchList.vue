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
  data: () => ({
    matches: [
      {
        id: 1,
        first: {
          name: 'Mike Carlson',
          avatar: 'https://cdn.vuetifyjs.com/images/lists/2.jpg'
        },
        second: {
          name: 'Cindy Baker',
          avatar: 'https://cdn.vuetifyjs.com/images/lists/3.jpg'
        }
      },
      {
        id: 2,
        first: {
          name: 'Ali Connors',
          avatar: 'https://cdn.vuetifyjs.com/images/lists/4.jpg'
        },
        second: {
          name: 'Joerge Carldone',
          avatar: 'https://cdn.vuetifyjs.com/images/lists/1.jpg'
        }
      }
    ]
  })
}
</script>