<template>
<div>
  <h1></h1>
  <todoList/>
</div>
</template>

<script>

import todoList from "./components/todoList.vue"
export default {
   name: "App" ,
   components: {
     todoList
}
}
</script>

<style>

body {
  background-color: rgb(66, 66, 66);
  color: aliceblue;
}

</style>

