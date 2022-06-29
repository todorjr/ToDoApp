<template>
  <div>
    <input
      type="text"
      id="task"
      placeholder="What is your task?"
      v-model="userInput"
    />
    <label for="task"></label>
    <button
      class="buttonClass"
      @click="addTask()"
      type="submit"
      title="Add task"
    >
      <i class="fa-solid fa-plus"></i>
    </button>

    <div class="tasks">
      <div class="taskOne">
        <h3>{{ titleLists }}</h3>
        <ul>
          <p v-if="tasks.length === 0">Your uncompleted tasks</p>
          <li v-for="task in tasks" :key="task">
            {{ task }}
            <button class="btn" @click="deleteTask()" type="submit">
              <i class="fa-solid fa-trash-can"></i>
            </button>
            <button class="btn" @click="completeTask()" type="submit">
              <i class="fa-solid fa-circle-check"></i>
            </button>
          </li>
        </ul>
      </div>
      <div class="taskTwo">
        <h3>{{ deletedTaskListTitle }}</h3>
        <ul>
          <li v-for="deleted in deletedTasks" :key="deleted">{{ deleted }}</li>
        </ul>
      </div>
      <div class="taskThree">
        <h3>{{ completeTaskListTitle }}</h3>
        <ul>
          <li v-for="complete in tasksCompleted" :key="complete">
            {{ complete }}
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "TaskList",
  data() {
    return {
      userInput: "",
      tasks: [],
      deletedTasks: [],
      tasksCompleted: [],
      titleLists: "Task list",
      deletedTaskListTitle: "Deleted task list",
      completeTaskListTitle: "Completed task list",
    };
  },
  methods: {
    addTask() {
      this.tasks.push(this.userInput);
      this.userInput = "";
    },
    deleteTask(task) {
      const deletedElement = this.tasks.splice(this.tasks.indexOf(task));
      this.deletedTasks.push(deletedElement[0]);
    },
    completeTask(task) {
      const completeElement = this.tasks.splice(this.tasks.indexOf(task));
      this.tasksCompleted.push(completeElement[0]);
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Kdam+Thmor+Pro&family=Quicksand:wght@300&display=swap");
.tasks {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  margin-top: 10px;
}
.taskOne,
.taskTwo,
.taskThree {
  background: rgba(255, 255, 255, 0.21);
  border-radius: 16px;
  box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
  backdrop-filter: blur(5px);
  -webkit-backdrop-filter: blur(5px);
  border: 1px solid rgba(255, 255, 255, 0.3);
  width: 40%;
  margin: 10px;
}
h3 {
  font-family: "Quicksand", sans-serif;
}
ul,
li {
  list-style-type: none;
  padding: 0;
  font-family: "Quicksand", sans-serif;
}
li {
  margin-left: 10px;
}

input {
  padding: 10px;
  font-size: 12px;
  border-width: 1px;
  border-color: #cccccc;
  background-color: #ffffff;
  color: #000000;
  border-style: solid;
  border-radius: 7px;
  box-shadow: 0px 0px 5px rgba(108, 108, 108, 0.75);
}
input:focus {
  outline: none;
}

.buttonClass {
  margin-left: 5px;
  font-size: 12px;
  font-family: Arial;
  width: 48px;
  height: 38px;
  border-width: 0px;
  color: #fff;
  border-bottom-left-radius: 17px;
  border-top-left-radius: 17px;
  border-top-right-radius: 17px;
  border-bottom-right-radius: 17px;
  text-shadow: 1px 1px 0px #2f6627;
  background: #095be9;
}

.buttonClass:hover {
  cursor: pointer;
}
.btn {
  float: right;
  border: none;
  background: transparent;
}
</style>
