<template lang="pug">
  .container
    div
      h1.title
        |nuxt-sample

      todo-list
        todo-list-item(
          v-for="todo in todos"
          :key="todo.id"
          :todo="todo"
        )
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import TodoList from '~/components/TodoList.vue'
import TodoListItem from '~/components/TodoListItem.vue'
import { Todo } from '~/models/Todo'

const components = {
  TodoList,
  TodoListItem
}

@Component({
  components
})
export default class Index extends Vue {
  todos: Todo[] = [
    {
      id: 1,
      text: 'buy the milk.',
      complete: false
    },
    {
      id: 2,
      text: 'read the magazine.',
      complete: false
    }
  ]
}
</script>

<style lang="scss">
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
