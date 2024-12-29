<template>
  <tr>
    <td class="text-center">2</td>
    <td>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Reiciendis ea c</td>
    <td class="text-center"><span class="badge badge-secondary">Small</span></td>
    <td>
      <button type="button" class="btn btn-warning">Edit</button>
      <button type="button" class="btn btn-danger">Delete</button>
    </td>
  </tr>
</template>

<script>
export default {
  name: 'TodoListItem',
  data() {
    return {
      //text: 'List Task'
    }
  }
}
</script>

<style></style>
