<template>
  <div id="app">
    <h1>{{ msg }}</h1>
    
    <tasks-component @calledParent="answerSon" :items="tasks" :title="'Categorias'"></tasks-component>

    <list-items-component :title="'Listagem de Algo'" :items="['Piso', 'Parede', 'Pia', 'Others']"></list-items-component>
  </div>
</template>

<script>
import TasksComponent from './components/TasksComponent'
import ListItemsComponent from './components/ListItemsComponent'

export default {
  name: 'app',
  data () {
    return {
      msg: 'Meu primeiro website em Vue',
      tasks: ['Cozinha', 'Banheiro', 'Sala de Estar']
    }
  },

  components: {
    TasksComponent,
    ListItemsComponent
  },
  methods: {
    answerSon(task) {
      this.tasks.push(task)
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
