<template>
  <div>
    <div class="card convo-card" v-for="(conversation, index) in conversations" :key="index" v-bind:class="conversation.postType">
      <div class="card-body">
        <p class="card-text">{{ conversation.postText }}</p>
        <router-link 
        v-for="(button, index) in conversation.postButtons" 
        :key="index" 
        v-bind:to="{ name: button.link }" 
        tag="button"
        class="btn btn-light btn-block btn-chat">
          {{ button.name }}
        </router-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ChatBot',
  data() {
    return {
      
    }
  },
  props: ['conversations']
}
</script>

<style>
.convo-card {
  margin-bottom: 20px;
  border-radius: 13px;
  font-weight: 700;
  padding: 0;
}
.convo-card > .card-body {
  padding: 2px;
}
.convo-card > .card-body > .card-text {
  padding: 16px;
  margin-bottom: 0;
}
.bot {
  background-color: #eaeaea;
  border: 1px solid #DFDFDF;
  color: #222;
  text-align: left
}
.cust {
  background-color: #02345F;
  color: white;
  text-align: left
}
.btn-chat {
  border: none;
  border-radius: 0;
  color: #2E64D1;
  height: 48px;
  margin: 0 0 2px !important;
  padding: 0 0 0 16px;
  text-align: left;
}
.btn-chat:last-child {
  border-radius: 0 0 10px 10px;
  margin-bottom: 0 !important;
}
</style>


