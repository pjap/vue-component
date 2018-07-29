<template>
  <div>
    <h4>You may edit the user here</h4>
    <p>Edit Me!</p>
    <hr>
    <p><strong>User Age : {{ userAge }}</strong></p>
    <hr>
    <button @click="editAge" class="btn btn-danger">Edit Age</button>
  </div>
</template>

<script>
import { eventBus } from '../main.js'

export default {
  props: {
    userAge: {
      type: Number
      // required: true,
      // default: 17
    }
  },
  methods: {
    editAge() {
      this.userAge = 25
      // this.$emit('ageWasEdit', this.age)
      // eventBus.$emit('ageWasEdit', this.userAge)
      eventBus.changeAge(this.userAge)
    }
  }
}
</script>

<style scoped>
  div {
    width: 500px;
    border: 1px solid black;
    padding: 30px;
    background-color: lightgreen;
  }
</style>
