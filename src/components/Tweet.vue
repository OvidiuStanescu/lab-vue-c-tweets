<template>
  <div class="tweet">
    <ProfileImage v-if="user" :image = "user.image"></ProfileImage>

    <div class="body">
      <div class="top">
        <User v-if="user" :userData ="user"></User>

        <Timestamp v-if="timestamp" :time = "timestamp"></Timestamp>
      </div>

      <Message v-if="message" :message="message"></Message>

      <Actions></Actions>
    </div>

    <i class="fas fa-ellipsis-h"></i>
  </div>
</template>

<script>

import Actions from "./Actions.vue"
import Message from "./Message.vue"
import ProfileImage from "./ProfileImage.vue"
import Timestamp from "./Timestamp.vue"
import User from "./User.vue"

export default{
  created() {
    this.user = this.tweet.user
    this.timestamp = this.tweet.timestamp
    this.message = this.tweet.message
  },
  data() {
    return{
      user: {},
      timestamp: "",
      message: ""
    }
  },
  components:{
    Actions,
    Message,
    ProfileImage,
    Timestamp,
    User
  },
  props: {
    tweet: {
      type: Object
    }
  }
}
</script>

<style scoped>
a {
  color: #42b983;
}
</style>
