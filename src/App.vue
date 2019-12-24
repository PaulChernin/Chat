<template>
  <div id="app">
    <Container>
      <ChatWindow @send-message="sendMessage">
        <!-- <ChatMessage v-for="message in sampleMessages" v-bind:key="message.id" v-bind:username="message.author" v-bind:datetime="message.datetime">{{message.text}}</ChatMessage> -->
        <ChatMessage v-for="message in messages" v-bind:key="message.id" v-bind:username="message.author" v-bind:datetime="message.datetime">{{message.text}}</ChatMessage>
      </ChatWindow>
    </Container>
  </div>
</template>

<script>
  //import HelloWorld from './components/HelloWorld.vue'

  import Container from './components/Container.vue'
  import ChatMessage from './components/ChatMessage.vue'
  import ChatWindow from './components/ChatWindow.vue'

  import axios from 'axios'

  export default {
    name: 'app',
    components: {
      //HelloWorld
      Container,
      ChatWindow,
      ChatMessage
    },
    mounted() {
      this.getMessages()
    },
    data() {
      return {
        messages: [{}],
        sampleMessages: [
          {
            id: '1',
            author: 'vasya',
            datetime: '1234',
            text: 'lolkek'
          }, {
            id: '2',
            author: 'petya',
            datetime: '12345',
            text: 'cheburek'
          }
        ]
      }
    },
    methods: {
      getMessages() {
        axios.get("http://188.225.47.187/api/chat/getmessages.php")
        .then( (response)=> {
          console.log('got')
            //let response = [{}]
            //let resp = JSON.parse(response.data)
            console.log('response', response)
          this.messages = response.data
        })
      },
      sendMessage(data) { 
        console.log('sent')
        axios.post('http://188.225.47.187/api/chat/sendmessage.php', {
          author: data.username,
          text: data.text
        })
        .then(() => {
          console.log('posted')
          this.getMessages()
        })

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
