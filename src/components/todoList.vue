<template>
  <div class="container">
      <div class="row">
          <div class="col-12">
              <p class="display-4">Your ToDo List!!!</p>
              <p>built in Vue.js...</p>
          </div>
      </div>
      <div class="row">
          <newTodo @on-addtodo="addTodo($event)"/>
      </div>
      <div class="row">
          <div class="col-12 col-lg-6">
           
              <ul class="list-group">
                  <todo v-for="(todo, index) in todos" 
                  :key="index"
                  :todoString="todo.todoString"
                  :completed="todo.completed"
                  @on-delete="deleteTodo(todo)"
                  @on-toggle="toggleTodo(todo)"
                  @on-edit="editTodo(todo, $event)"
                  /> 
              </ul>
              
          </div>
      </div>
  </div>
</template>

<script>
import todo from "./todo"
import newTodo from "./newTodo"
export default {
    components: {
        todo,
        newTodo
    },
  data(){
      return {
          todos: [
              {todoString: "Make tea", completed: false},
              {todoString: "Water plants", completed: true},
              {todoString: "stay calm", completed: true},
              {todoString: "sleep idiot", completed: false}
          ]
      }
  },
  methods:{
      addTodo (newTodo){
          this.todos.push({
              todoString: newTodo,
              completed: false
          })
      },
      toggleTodo (todo){
          todo.completed = !todo.completed;
      },
      editTodo (todo, newTodoString){
          todo = newTodoString;
      },
      deleteTodo (deleteTodo){
          this.todos = this.todos.filter( todo => todo.todoString !== deleteTodo.todoString);
      }
  }
};
</script>

<style>

</style>

