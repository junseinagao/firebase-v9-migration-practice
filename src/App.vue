<template>
  <div class="app">
    <button v-on:click="postTweet">ツイート</button>
    <div>
      <p v-for="tweet in tweets" :key="tweet.id">
        {{ tweet.text }}
      </p>
    </div>
  </div>
</template>

<script>
import firebase from "firebase";

export default {
  data() {
    return {
      tweets: [],
    };
  },
  methods: {
    postTweet() {
      const tweet = {
        text: "こんにちは、ツイートの本文です。",
      };
      firebase
        .firestore()
        .collection("tweets")
        .add(tweet)
        .then((ref) => {
          this.tweets.push({
            id: ref.id,
            ...tweet,
          });
        });
    },
  },
  created() {
    firebase
      .firestore()
      .collection("tweets")
      .get()
      .then((snapshot) => {
        snapshot.docs.forEach((doc) => {
          this.tweets.push({
            id: doc.id,
            ...doc.data(),
          });
        });
      });
  },
};
</script>
