<template>
  <div id="app">
      <ViewChange @toggleBtnClicked="handleViewChange"/>
      <h2>Tweets:</h2>
      <TweetComp :class="[{displayView: isGrid}]" v-for="tweet in tweets" 
      :key="tweet.content"
      :tweetContent="tweets.content"
      :tweetUser="tweets.user"
      :tweetDate="tweets.date"

      />
  </div>
</template>

<script>
import TweetComp from './components/TweetComp.vue'
import ViewChange from './components/ViewChange.vue'

export default {
  name: 'App',
  components: {
    TweetComp,
    ViewChange
  },
  data: function() {
    return {
      displayView: 'isGrid',
      isGrid: true,

      tweets: [
        {
          content: "This is my first tweet",
          user: "Jane",
          date: "Aug 14, 2021"
        },
        {
          content: "I really do not understand the appeal of Twitter",
          user: "Unkown_99",
          date: "Jul 14, 2021"
        },
        {
          content: "What did the shark say when it ate the clownfish?....It tastes a little funny",
          user: "joker23",
          date: "Apr 1, 2021"
        }
      ]
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>