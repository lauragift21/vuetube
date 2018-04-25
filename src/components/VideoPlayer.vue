<template>
  <div class="video-player">
    <div class="video-container">
      <iframe width="840" height="360" :src="this.activeVideo.youtubeURL" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
      <h3>{{ this.activeVideo.title }}</h3>
      <div class="row">
        <p> {{ this.activeVideo.views }} Views</p>
        <p> {{ this.activeVideo.likes }} <button @click="addLike">Likes</button></p>
      </div>
    </div>
    <div class="video-list">
      <div @click="chooseVideo(video)" :key="video.id" v-for="video in videos" class="thumbnail">
        <div class="thumbnail-img">
          <img :src="video.thumbnail" alt="video"/>
        </div>
        <div class="thumbnail-info">
          <h3>{{ video.title }}</h3>
          <p>{{ video.creator }}</p>
          <p class="thumbnail-views"> {{ video.views }} Views</p>
          <p class="thumbnail-views"> {{ video.duration }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
let videos = [
  {
    id: 1,
    title: '18-core iMac Pro Review: Not a Trap!',
    thumbnail:
      'https://i.ytimg.com/vi/jn9mHzXJIV0/hqdefault.jpg?sqp=-oaymwEZCNACELwBSFXyq4qpAwsIARUAAIhCGAFwAQ==&rs=AOn4CLAvJvk4k_UNB9nst4pFP-txM1TLZA',
    youtubeURL: 'https://www.youtube.com/embed/jn9mHzXJIV0',
    creator: 'Marques Brownlee',
    likes: 0,
    views: 0,
    duration: '3 days ago'
  },
  {
    id: 2,
    title: 'Dope Tech: Camera Robots!',
    thumbnail:
      'https://i.ytimg.com/vi/UIwdCN4dV6w/hqdefault.jpg?sqp=-oaymwEZCNACELwBSFXyq4qpAwsIARUAAIhCGAFwAQ==&rs=AOn4CLDhlan32jHSvicGZezDFPjAOdXGUA',
    youtubeURL: 'https://www.youtube.com/embed/UIwdCN4dV6w',
    creator: 'Marques Brownlee',
    likes: 0,
    views: 0,
    duration: '2 days ago'
  },
  {
    id: 3,
    title: "MY NANNY DRAMA | I'VE HAD 4 WITHIN 6 MONTHS | HOUSE HELP DIARIES",
    thumbnail: 'http://img.youtube.com/vi/KPVfCZST84U/0.jpg',
    youtubeURL: 'https://www.youtube.com/embed/KPVfCZST84U',
    creator: 'SiSi Yemmie',
    likes: 0,
    views: 0,
    duration: '3 weeks ago'
  },
  {
    id: 4,
    title: 'iPhone 8 Plus vs iPhone 7 Plus Full Comparison',
    thumbnail: 'http://img.youtube.com/vi/am3i3bPMWXM/0.jpg',
    youtubeURL: 'https://www.youtube.com/embed/am3i3bPMWXM',
    creator: 'Marques Brownlee',
    likes: 0,
    views: 0,
    duration: '1 week ago'
  },
  {
    id: 5,
    title: 'The Apple Ecosystem: Explained!',
    thumbnail:
      'https://i.ytimg.com/vi/KB4_WIPE7vo/hqdefault.jpg?sqp=-oaymwEZCNACELwBSFXyq4qpAwsIARUAAIhCGAFwAQ==&rs=AOn4CLCCxXm7aoPShOwON74nhMlGYMUkHw',
    youtubeURL: 'https://www.youtube.com/embed/KB4_WIPE7vo',
    creator: 'Marques Brownlee',
    likes: 0,
    views: 0,
    duration: '3 weeks ago'
  },
  {
    id: 6,
    title: 'Talking Tech with Neil deGrasse Tyson!',
    thumbnail:
      'https://i.ytimg.com/vi/pqQrL1K0Z5g/hqdefault.jpg?sqp=-oaymwEZCNACELwBSFXyq4qpAwsIARUAAIhCGAFwAQ==&rs=AOn4CLA5hTiwkz4Tr1w1hSMhPlwtmQeyYw',
    youtubeURL: 'https://www.youtube.com/embed/pqQrL1K0Z5g',
    creator: 'Marques Brownlee',
    likes: 0,
    views: 0,
    duration: '3 days ago'
  }
]

export default {
  name: 'VideoPlayer',
  data () {
    return {
      videos,
      activeVideo: videos[0]
    }
  },
  methods: {
    chooseVideo (video) {
      // SET VIDEO AS ACTIVE VIDEO
      this.activeVideo = video
      // INCREASE VIEWS BY +1
      video.views += 1
    },
    addLike () {
      this.activeVideo.likes += 1
    }

  }
}
</script>

<style scoped>
.video-player {
  display: flex;
  width: 1200px;
  margin: auto;
}
.video-container {
  margin-right: 30px;
}
.row {
  display: flex;
  justify-content: space-between;
}
button {
  border-radius: 3px;
  background:crimson;
  color:white;
  border:none;
  padding:10px 10px;
  cursor: pointer;
}
.thumbnail {
  display: flex;
}
.thumbnail img {
  width: 157px;
  cursor: pointer;
}
.thumbnail-info {
  margin-left: 16px;
}
.thumbnail h3 {
  font-size: 16px;
}
h3,p{
  margin:0;
  padding:0;
}
.thumbnail-views{
  font-size:14px;
}
</style>
