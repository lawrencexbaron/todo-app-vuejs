<template>
  <div class="wrapper">
    <form @submit.prevent="addTodoItem">
      <div class="mx-auto flex justify-items-center mt-10 p-10">
        <div
          class="bg-white border-1 border-gray-500 shadow-md px-5 py-6 mx-auto"
        >
          <input
            type="text"
            class="border-1 border-gray-500 px-2 py-1 w-full"
            placeholder="Add todo item"
            v-model="todoItem"
          />
          <button
            class="bg-blue-500 text-white px-2 py-1 rounded w-full mt-2"
            @click="addTodoItem"
          >
            Add Todo Item
          </button>

          <div class="mt-5">
            <div
              v-for="(item, index) in this.todoList"
              :key="index"
              class="flex items-center justify-between gap-5 mb-2"
            >
              <div class="flex items-center">
                <input
                  type="checkbox"
                  class="mr-2"
                  :checked="item.completed"
                  @change="updateTodoItem(item)"
                />
                <span
                  :class="{ 'line-through': item.completed }"
                  class="text-gray-500"
                >
                  {{ item.title }}
                </span>
              </div>
              <button
                class="bg-red-500 text-white px-2 py-1 rounded"
                @click="deleteTodoItem(item)"
              >
                Delete
              </button>
            </div>
          </div>
        </div>
      </div>
    </form>
  </div>
</template>
<script>
export default {
  name: "home",
  data() {
    return {
      todoList: [],
    };
  },
  methods: {
    addTodoItem() {
      // Add validation for empty todo item here then add it to the todoList array
      if (this.todoItem) {
        this.todoList.push({
          title: this.todoItem,
          completed: false,
        });
        this.todoItem = "";
      }
    },
    updateTodoItem(item) {
      item.completed = !item.completed;
    },
    deleteTodoItem(item) {
      this.todoList = this.todoList.filter((todo) => todo !== item);
    },
  },
};
</script>
