<template lang="pug">
  li
    input(
      type="checkbox"
      v-model="todo.complete"
    )
    |{{ todo.text }}
</template>

<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator'
import { Todo } from '~/models'

@Component
export default class TodoListItem extends Vue {
  @Prop(Array) readonly todo!: Todo[] | undefined
}
</script>
