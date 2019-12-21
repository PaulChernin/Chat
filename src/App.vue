<template>
  <div id="app">
    <Container>
      <ChatWindow>
        <ChatMessage username="Ivan" time="21.12.2019 05:00:50">Hello, World!!!</ChatMessage>
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
