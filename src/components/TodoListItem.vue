<template>
  <tr>
    <td class="text-center">{{ index }}</td>
    <td>{{ task.name }}</td>
    <td class="text-center"><span :class="['badge', level.class]">{{ level.text }}</span></td>
    <td>
      <button type="button" class="btn btn-warning">Edit</button>
      <button type="button" class="btn btn-danger" v-on:click="handleDelete(task.id)">Delete</button>
    </td>
  </tr>
</template>

<script>
import listLevel from '../mockdatas/listLevel';
export default {
  name: 'TodoListItem',
  props: {
    task: {
      type: Object,
      default: null
    },
    index: {
      type: Number,
      default: 1
    }
  },
  data() {
    return {
      //text: 'List Task'
    }
  },
  methods: {
    handleDelete(id) {
      this.$emit('handleDelete', id);
    }
  },
  computed: {
    level() {
      const level = listLevel.find(level => level.value === this.task.level);
      return level ? level : listLevel.find(level => level.value === 99);
    }
  }
}
</script>

<style></style>
