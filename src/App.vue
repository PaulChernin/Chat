<template>
  <div id="app">
    <Container>
      <ChatWindow @send-message="sendMessage">
        <ChatMessage v-for="message in data" username="Ivan" :datetime="datetime">{{message}}</ChatMessage>
      </ChatWindow>
    </Container>
  </div>
</template>

<script>
  //import HelloWorld from './components/HelloWorld.vue'

  import Container from './components/Container.vue'
  import ChatMessage from './components/ChatMessage.vue'
  import ChatWindow from './components/ChatWindow.vue'

  export default {
    name: 'app',
    components: {
      //HelloWorld
      Container,
      ChatWindow,
      ChatMessage
    },
    methods: {
      sendMessage() {  
        obj.nickname , obj.message
        axios.post('')

      }
    }
  }
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
  body {
    margin: 0;
    background-color: #f9f9fa;
  }
</style>
