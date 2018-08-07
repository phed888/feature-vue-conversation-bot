<template>
  <div>
    <div class="card convo-card" v-for="(conversation, index) in conversations" :key="index" v-bind:class="conversation.postType">
      <div class="time-stamp">{{ conversation.postTime }}</div>
      <div class="brand-logo"></div>
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
  margin: 30px 0 20px;
  border-radius: 13px;
  font-weight: 300;
  padding: 0;
  position: relative;
}
.convo-card.bot {
  margin-left: 40px;
  margin-right: 20%;
}
.convo-card.cust {
  margin-left: 25%;
}
.convo-card .time-stamp {
  font-size: 12px;
  color: #999999;
  position: absolute;
  top: -22px;
}
.convo-card.bot .time-stamp::before {
  content: 'Expedia.com '
}
.convo-card.cust .time-stamp {
  right: 0;
}
.bot .brand-logo {
  position: absolute;
  background-image: url("../assets/logo-expedia.png");
  height: 32px;
  width: 32px;
  top: 0;
  left: -40px;
}
.convo-card > .card-body {
  padding: 2px;
  text-align: left;
}
.convo-card > .card-body > .card-text {
  padding: 16px;
  line-height: 21px;
  margin-bottom: 0;
}
.bot {
  background-color: #eaeaea;
  border: 1px solid #DFDFDF;
  color: #222;
  
}
.cust {
  background-color: #02345F;
  color: white;
  
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


