<template>
<div>
  <Navbar />
  <v-container fluid>
      <h3 class="headline font-weight-medium mb-2">Recommended</h3>
      <v-row>
        <v-col
          cols="12"
          sm="6"
          md="4"
          lg="3"
          v-for="i in loading ? 10 : 12"
          :key="i"
          class="mx-xs-auto"
        >
          <v-skeleton-loader type="card-avatar" :loading="loading">
            <video-card
              :card="{ maxWidth: 350 }"
              :video="video"
              :channel="channel"
            ></video-card>
          </v-skeleton-loader>
        </v-col>
      </v-row>
    </v-container>
</div>
</template>

<script>
  import Navbar from '../components/Navbar'
  import videoCard from '@/components/VideoCard'

  export default {
    name: 'Home',
  data: () => ({
    loading: true,
    video: {
    id: 1,
    url: '/videoPlay',
    title: "znation31",
    thumbnail:
      "https://i.ytimg.com/vi/jn9mHzXJIV0/hqdefault.jpg?sqp=-oaymwEZCNACELwBSFXyq4qpAwsIARUAAIhCGAFwAQ==&rs=AOn4CLAvJvk4k_UNB9nst4pFP-txM1TLZA",
    youtubeURL: "https://www.youtube.com/embed/jn9mHzXJIV0",
    creator: "elijahVR",
    likes: 0,
    createdAt: '1 hour ago',
    subscribers: '100B',
    views: 14526,
    description:
          'N/A'
  },
    channel: {
      url: '/channel',
      avatar: 'profile.png'
    }
  }),
    components: {
      Navbar,
      videoCard
    },
    mounted() {
    setTimeout(() => {
      this.loading = false
    }, 2000)
    }
  }
</script>
<style lang="scss">

</style>
