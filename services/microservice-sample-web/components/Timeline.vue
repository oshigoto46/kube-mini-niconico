<template>
  <v-container fluid grid-list-xs>
    <v-layout justify-center row wrap>
      <v-flex v-for="tweet in timeline" :key="tweet._id" class="tweet" xs12>
        <tweet :tweet="tweet" />
      </v-flex>
      <v-flex v-for="tweet2 in timeline" :key="tweet2._id" class="tweet" xs12>
        <tweet :tweet="tweet" />
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
import Tweet from '~/components/Tweet.vue'
export default {
  components: {
    Tweet
  },
  data() {
    return {
      timeline: [],
      dummy   : [],
      message: 'Hello World'
    }
  },
  async mounted() {
    this.timeline = await this.$axios.$get('/api/timeline')
    this.dummy = await this.$axios.$get('/api/timeline')
  },
  methods: {
    async update() {
      this.timeline = await this.$axios.$get('/api/timeline')
    }
  }
}
</script>

<style>
.tweet {
  margin: 4px;
}
</style>
