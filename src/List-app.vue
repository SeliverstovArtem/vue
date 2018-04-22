<template lang="pug">
  div.list
    p Список статей:
    div(v-for="i in articles").list--article
      span.list--title {{i.title}}
      span.list--text {{i.text}}
    div
      button.btn.new(@click="add").fa.fa-plus.fa-2x
</template>

<script>
export default {
  props: ['articles'],
  data () {
    return {

    }
  },
  methods: {
    add () {
      this.$emit('new')
    }
  }
}
</script>

<style lang="sass">
  .list
    .list--article
      display: grid
      justify-content: center
      grid: "title text" 50px / 20% 60%
      .list--title
        font-weight: bold
        align-self: center
      .list--text
        align-self: center
</style>
