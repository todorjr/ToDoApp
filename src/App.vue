<template>
  <div id="app">
    <HeaderPage title="Todo App" />
    <TaskList />
  </div>
</template>

<script>
import HeaderPage from "./components/HeaderPage.vue";
import TaskList from "./components/TaskList.vue";

export default {
  name: "App",
  components: {
    HeaderPage,
    TaskList,
  },
};
</script>

<style>
#app {
  text-align: center;
  border-radius: 20px;
  height: 100vh;
  width: 80%;
  margin: auto;
  box-shadow: 8px 10px 29px 4px rgba(0, 0, 0, 0.75);
  -webkit-box-shadow: 8px 10px 29px 4px rgba(0, 0, 0, 0.75);
  -moz-box-shadow: 8px 10px 29px 4px rgba(0, 0, 0, 0.75);
  background-image: url("https://images.unsplash.com/photo-1507925921958-8a62f3d1a50d?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2952&q=80");
  background-size: cover;
}
</style>
