<template lang="pug">
  main
    h1 {{message}}
    //- div.component
    transition(name="slide-fade")
      component(:is="name" @create="save" v-bind:articles="articles" @new="add")
</template>

<script>
import ArticleApp from "./Article-App.vue"
import ListApp from "./List-App.vue"
export default {
  props: ['message'],
  data () {
    return {
      articles: [],
      name: "article-app",
    }
  },
  methods: {
    save (article) {
      this.articles.push(article)
      this.name = "list-app"
      console.log(this.articles)
    },
    add () {
      this.name = "article-app"
    }
  },
  components: {
    ArticleApp,
    ListApp
  }
}
</script>

<style lang="sass">
  main
    display: grid
    grid: "h1" 5em "article" 1fr / auto
    overflow: hidden

  .slide-fade-enter-active
    transition: all .5s ease-in-out

  .slide-fade-leave-active
    transition: all .5 ease-in-out

  .slide-fade-leave-to
    opacity: 0

  .slide-fade-enter
    transform: translateX(-100%)
    opacity: 0
</style>
