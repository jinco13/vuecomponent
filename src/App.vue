<template>
  <div id="app">
    <h1>{{ msg }}</h1>
    <NewQuote :quotes="quotes" v-on:updateView="updateParentView"></NewQuote>
    <QuoteGrid :quotes="quotes">
        <h2 slot="title">hoge</h2>
        <p slot="content">hoge</p>    
    </QuoteGrid>
    <component :is="currentView">
    </component>
  </div>
</template>

<script>
import NewQuote from './components/NewQuote'
import QuoteGrid from './components/QuoteGrid'
import TestView from './components/TestView'
import AnotherTestView from './components/AnotherTestView'

export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      quotes: ["This is my Quote"],
      currentView: TestView
    }
  },
  components: {
    NewQuote,
    QuoteGrid,
    TestView,
    AnotherTestView
  },
  methods: {
    updateParentView: function(param) {
        alert(param);
        this.currentView = AnotherTestView;
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

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
