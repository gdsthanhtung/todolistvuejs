<template>
  <b-col cols="12" lg="6">
    <!-- ADD : START -->
    <form-add-button v-bind:isShowForm="isShowForm" v-on:handleShowForm="handleShowForm"  />
    <!-- ADD : END -->

    <form v-if="isShowForm" method="POST" class="form-inline justify-content-between">
      <div class="form-group">
        <label class="sr-only" for="">label</label>
        <input type="text" class="form-control" placeholder="Task Name" v-model="taskName" />
      </div>
      <div class="form-group">
        <label class="sr-only" for="">label</label>
        <b-form-select v-model="selectedLevel" :options="levels"></b-form-select>
      </div>

      <button type="button" class="btn btn-primary">Submit</button>
      <button v-on:click="handleShowForm()" type="button" class="btn btn-secondary">Cancel</button>
    </form>
  </b-col>

</template>

<script>
import FormAddButton from './FormAddButton.vue';
import listLevel from '../mockdatas/listLevel';
export default {
  name: 'CompForm',
  components: {
    FormAddButton
  },
  props: {
    isShowForm: {
      type: Boolean,
      default: false
    }
  },
  data() {
    return {
      selectedLevel: null, // https://bootstrap-vue.org/docs/components/form-select#form-select
      listLevel,
      taskName: ''
    };
  },
  methods: {
    handleShowForm() {
      this.resetForm();
      this.$emit('handleShowForm');
    },
    resetForm() {
      this.selectedLevel = null;
      this.taskName = '';
    }
  },
  computed: {
    levels() {
      this.listLevel = this.listLevel.filter(level => level.value !== 99);
      return [{ value: null, text: 'Select a Level' }, ...this.listLevel];
    }
  }
};
</script>

<style></style>
