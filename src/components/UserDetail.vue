<template>
  <div>
    <h4>You may view the user detail here</h4>
    <p>Many Details</p>
    <hr>
    <p><strong>Child Name: {{ name }}</strong></p>
    <hr>
    <p><strong>User Age : {{ userAge }}</strong></p>
    <!-- <p><strong>Reverse Child Name : {{ switchName() }}</strong></p> -->
    <hr>
    <button @click="resetName" class="btn btn-warning">Reset Name</button>
    <button @click="resetFn()" class="btn btn-warning">Reset Name But With Callback</button>
  </div>
</template>

<script>
import { eventBus } from '../main.js'

export default {
  props: {
    name: {
      type: String,
      required: true,
      default: 'Bung Bung'
    },
    // Avoid A Custom Event Using Callback Function In Child
    resetFn: Function,
    userAge: {
      type: Number
      // required: true,
      // default: 17
    }
  },
  methods: {
    switchName() {
      return this.name.split("").reverse().join("")
    },
    resetName() {
      this.name = "Prana Jaya"
      this.$emit('NameResetChild', this.name)
    }
  },
  created() {
    eventBus.$on('ageWasEdit', (age) => {
      this.userAge = age
    });
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
