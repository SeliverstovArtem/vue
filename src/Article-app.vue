<template lang="pug">
  article.article
    div.article--title
      input.article--title__edit(v-model="title" placeholder="Название" autofocus transition="title")
    div.article--menu
    div.article--text
      textarea.article--text__edit.edit(v-model="text" @input="edit")
    div.article--send
      transition(name="fade")
        button.btn.create(v-if="text" @click="save" transition="title").fa.fa-check.fa-2x
</template>

<script>
export default {
  data () {
    return {
      title: "",
      text: "",
    }
  },
  methods: {
    edit () {
      console.log(this.text)
    },
    save () {
      this.$emit('create', {title: this.title, text: this.text})
      this.text = ""
      this.title = ""
    }
  }
}
</script>

<style lang="sass">
  article
    display: grid
    grid: "title" 2em "menu" 2em "text" 1fr "send" 75px / calc(100% - 10em)
    justify-content: center
    align-content: center
    .article--title
      justify-self: start
      width: 50%
      align-self: end
      .article--title__edit
        width: 100%
        border: none
        border-bottom: 2px solid #fff
        outline: none
        font-size: 1.5em
        transition: 0.5s ease-in-out
        &::-webkit-input-placeholder
          color: #ccc
        &:focus
          border-bottom: 2px solid #eee
          transition: 0.5s ease-in-out
    .article--text__edit
      font-family: 'Avenir', Helvetica, Arial, sans-serif
      width: 100%
      resize: none
      font-size: 1.2rem
      height: 100%
      border: none
      border-bottom: 2px solid #ccc
      &:focus
        outline: none
    .article--send
      margin: 0 0
      display: grid
  .btn
        background: #fff
        border: none
        margin: 0
        padding: 0
        border-radius: 50%
        width: 50px
        height: 50px
        transition: 0.5s ease-in-out
        justify-self: end
        align-self: center
        &:hover
          background: #eee
          transition: 0.5s ease-in-out
        &:active
          // background: #ddd
          box-shadow: inset 0 0 25px 5px #ddd

  .fade-enter-active, .fade-leave-active
    transition: opacity .5s
  .fade-enter, .fade-leave-to
    opacity: 0

</style>
