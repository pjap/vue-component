<template>
  <div>
    <h4>You may view the user detail here</h4>
    <p>Many Details</p>
    <p>User Name: {{ name }}</p>
    <p>Reverse User Name : {{ switchName() }}</p>
  </div>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      required: true,
      default: 'Bung Bung'
    }
  },
  methods: {
    switchName() {
      return this.name.split("").reverse().join("")
    }
  }
}
</script>

<style scoped>
  div {
    width: 500px;
    border: 1px solid black;
    padding: 30px;
    background-color: lightcoral;
  }
</style>
