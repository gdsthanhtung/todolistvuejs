<template>
  <b-col cols="12">
    <div class="form-group">
      <div class="dropdown">
        <b-dropdown id="dropdown-1" text="Sort by" class="">
          <b-dropdown-item>Name ASC</b-dropdown-item>
          <b-dropdown-item>Name DESC</b-dropdown-item>
          <b-dropdown-divider></b-dropdown-divider>
          <b-dropdown-item active>Level ASC</b-dropdown-item>
          <b-dropdown-item>Level DESC</b-dropdown-item>
        </b-dropdown>
        <span class="badge badge-success badge-medium">NAME - DESC</span>
      </div>
    </div>
  </b-col>
</template>

<script>
export default {
  name: 'ControlSort',
  data() {
    return {
      //text: ''
    }
  }
}
</script>

<style></style>
