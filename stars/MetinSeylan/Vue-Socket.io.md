---
project: Vue-Socket.io
stars: 3930
description: 😻 Socket.io implementation for Vuejs and Vuex
url: https://github.com/MetinSeylan/Vue-Socket.io
---

Vue-Socket.io is a socket.io integration for Vuejs, easy to use, supporting Vuex and component level socket consumer managements.

###### Demo

-   Chat Application
-   Car Tracking Application

You can also check my other npm library Nestjs OpenTelemetry

are you looking for old documentation? it's here

#### 🚀 Installation

npm install vue-socket.io --save

##### Using Connection String

import Vue from 'vue'
import store from './store'
import App from './App.vue'
import VueSocketIO from 'vue-socket.io'

Vue.use(new VueSocketIO({
    debug: true,
    connection: 'http://metinseylan.com:1992',
    vuex: {
        store,
        actionPrefix: 'SOCKET\_',
        mutationPrefix: 'SOCKET\_'
    },
    options: { path: "/my-app/" } //Optional options
}))

new Vue({
    router,
    store,
    render: h \=> h(App)
}).$mount('#app')

##### Using socket.io-client Instance

import Vue from 'vue'
import store from './store'
import App from './App.vue'
import VueSocketIO from 'vue-socket.io'
import SocketIO from 'socket.io-client'

const options \= { path: '/my-app/' }; //Options object to pass into SocketIO

Vue.use(new VueSocketIO({
    debug: true,
    connection: SocketIO('http://metinseylan.com:1992', options), //options object is Optional
    vuex: {
      store,
      actionPrefix: "SOCKET\_",
      mutationPrefix: "SOCKET\_"
    }
  })
);

new Vue({
    router,
    store,
    render: h \=> h(App)
}).$mount('#app')

**Parameters**

**Type's**

**Default**

**Required**

**Description**

debug

Boolean

`false`

Optional

Enable logging for debug

connection

String/Socket.io-client

`null`

Required

Websocket server url or socket.io-client instance

vuex.store

Vuex

`null`

Optional

Vuex store instance

vuex.actionPrefix

String

`null`

Optional

Prefix for emitting server side vuex actions

vuex.mutationPrefix

String

`null`

Optional

Prefix for emitting server side vuex mutations

#### 🌈 Component Level Usage

If you want to listen socket events from component side, you need to add \`sockets\` object in Vue component. After that every function will start to listen events, depends on object key

new Vue({
    sockets: {
        connect: function () {
            console.log('socket connected')
        },
        customEmit: function (data) {
            console.log('this method was fired by the socket server. eg: io.emit("customEmit", data)')
        }
    },
    methods: {
        clickButton: function (data) {
            // $socket is socket.io-client instance
            this.$socket.emit('emit\_method', data)
        }
    }
})

##### Dynamic Listeners

If you need consuming events dynamically in runtime, you can use \`subscribe\` and \`unsubscribe\` methods in Vue component

this.sockets.subscribe('EVENT\_NAME', (data) \=> {
    this.msg \= data.message;
});

this.sockets.unsubscribe('EVENT\_NAME');

##### Defining handlers for events with special characters

If you want to handle 'kebab-case', or "event with space inside it" events, then you have to define it via the following way

export default {
  name: 'Test',
  sockets: {
    connect: function () {
      console.log('socket to notification channel connected')
    },
  },

  data () {
    return {
      something: \[
         // ... something here for the data if you need.
      \]
    }
  },

  mounted () {
    this.$socket.subscribe("kebab-case", function(data) {
        console.log("This event was fired by eg. sio.emit('kebab-case')", data)
    })
  }
}

#### 🏆 Vuex Integration

When you set store parameter in installation, \`Vue-Socket.io\` will start sending events to Vuex store. If you set both prefix for vuex, you can use \`actions\` and \`mutations\` at the same time. But, best way to use is just \`actions\`

import Vue from 'vue'
import Vuex from 'vuex'

Vue.use(Vuex)

export default new Vuex.Store({
    state: {},
    mutations: {
        "<MUTATION\_PREFIX><EVENT\_NAME>"() {
            // do something
        }
    },
    actions: {
        "<ACTION\_PREFIX><EVENT\_NAME>"() {
            // do something
        }
    }
})

Stargazers over time
--------------------
