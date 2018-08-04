<template>
  <div class="chat-conversation">
    <ChatBot v-bind:conversations="conversations"/>
  </div>
</template>

<script>
import data from '@/data/conversation'
import ChatBot from '@/components/ChatBot'

export default {
  name: 'ChatConversation',
  data() {
    return {
      conversations: data
    }
  },
  components: {
    ChatBot
  }
}
</script>

<style>
.chat-conversation {
  background-color: #fff;
  margin: 0 auto;
  padding: 20px;
  width: 375px;
  height: 100vh;
}
</style>


