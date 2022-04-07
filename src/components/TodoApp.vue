<template>
  <div class="todo">
    <h3>My TO-Do App</h3>
    <input class="input" v-model="task" placeholder="Enter your Task" />
    <button class="create" @click="createTaskFn">Create</button>
    <div class="arraylist" v-for="(array, index) in todoArray" :key="index">
      <span>{{ index + 1 }}.</span>
      <span class="arraylist">{{ array.task }}</span>
      <button class="deletebtn" @click="deleteTaskFn(index)">Delete</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      task: "",
      todoArray: [
        // {
        //   task: "new task 1",
        // },
        // {
        //   task: "new task 2",
        // },
        // {
        //   task: "new task 3",
        // },
      ],
    };
  },
  methods: {
    createTaskFn() {
      if (this.task.length === 0) {
        alert("Please enter a Task");
      } else {
        this.todoArray.push({
          task: this.task,
        });
        this.task = "";
      }
    },
    deleteTaskFn(ind) {
      // console.log(ind);

      this.todoArray.splice(ind, 1);
    },
  },
};
</script>

<style>
.input {
  width: 6cm;
  color: black;
}
.create {
  margin-left: 3pt;
  color: wheat;
  background: green;
}
.arraylist {
  margin-top: 3pt;
  margin-left: 5pt;
}
.deletebtn {
  margin-left: 6pt;
  color: red;
  border-radius: 0.5px;
}
</style>