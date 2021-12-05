<template>
  <v-main>
    <v-container>
      <v-card>
        <v-card-title>
          <h2>Add new task</h2>
        </v-card-title>
        <v-card-text>
          <v-form class="px-3">
            <div v-if="!isEditing">
              <v-text-field label="task" v-model="todo"> </v-text-field>

              <v-btn flat class="success mx-0 mt-2" @click="storeTodo"
                >Add</v-btn
              >
            </div>

            <div v-else>
              <v-text-field v-model="todo"></v-text-field>
              <v-btn
                flat
                class="success mx-0 mt-2"
                type="submit"
                @click="updateTodo"
                >Update</v-btn
              >
            </div>
          </v-form>
        </v-card-text>
      </v-card>

      <v-card class="mx-auto" tile>
        <v-list-item v-for="(todo, index) in todos" v-bind:key="todo">
          <v-list-item-content>
            <v-list-item-title
              ><v-icon>mdi-bird</v-icon> {{ todo }}
              <v-btn @click="editTodo(index, todo)" class="ml-2 mr-2d success"
                >Edit</v-btn
              >
              <v-icon large color="orange darken-2"> mdi-call-split </v-icon>
              <v-btn class="ml-2 mr-2d success" @click="removeTodo(index)"
                >Delete</v-btn
              >
            </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-card>
    </v-container>
  </v-main>
</template>

<script>
export default {
  data: () => ({
    isEditing: false,
    todo: "",
    todos: [],
    selectedTodo: null,
  }),

  methods: {
    storeTodo() {
      if (this.todo === "") return;
      this.todos.push(this.todo);
      this.todo = "";
    },

    removeTodo(index) {
      this.todos.splice(index, 1);
    },

    updateTodo() {
      this.todos.splice(this.selectedIndex, 1, this.todo);
      this.todo = "";
      this.isEditing = false;
    },

    editTodo(index, todo) {
      this.isEditing = true;
      this.todo = todo;
      this.selectedIndex = index;
      console.log(this.todo);
    },
  },
};
</script>
