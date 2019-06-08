<template lang="pug">
  li
    |{{ todo.text }}
</template>

<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator'
import { Todo } from '~/models/Todo'

@Component
export default class TodoListItem extends Vue {
  @Prop(Array) readonly todo!: Todo[] | undefined
}
</script>
