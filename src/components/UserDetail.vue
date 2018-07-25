<template>
  <div>
    <h4>You may view the user detail here</h4>
    <p>Many Details</p>
    <p>User Name : {{ name }}</p>
  </div>
</template>

<script>
export default {
  props: ['name']
}
</script>

<style scoped>
  div {
    width: 500px;
    border: 1px solid black;
    padding: 30px;
    background-color: tomato;
  }
</style>
