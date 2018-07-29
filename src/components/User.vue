<template>
  <div class="component">
    <h1>The User Components</h1>
    <p>I'm An Awesome User!</p>
    <button class="btn btn-info" @click="changeName">Change Name</button>
    <hr>
    <p><strong>Parent Name : {{ realName }}</strong></p>
    <p><strong>Parent Age : {{ age }}</strong></p>
    <hr>
    <div class="row">
      <div class="col-xs-12 col-sm-6">
        <appUserDetail :name="realName" @NameResetChild="realName = $event" :resetFn="resetName" :userAge="age"></appUserDetail>
      </div>
      <div class="col-xs-12 col-sm-6">
        <appUserEdit :userAge="age" @ageWasEdit="age = $event"></appUserEdit>
      </div>
    </div>
  </div>
</template>

<script>
import { eventBus } from '../main.js'
import UserDetail from '../components/UserDetail.vue'
import UserEdit from '../components/UserEdit.vue'

export default {
  data: function() {
    return {
      realName: 'Prana Jaya',
      age: 24
    }
  },
  methods: {
    changeName() {
      this.realName = 'Anna'
    },
    // Using Callback
    resetName() {
      this.realName = 'Prana Jaya'
    }
  },
  components: {
    appUserDetail: UserDetail,
    appUserEdit: UserEdit
  },
  // For Same Edit If Child And Parent Want Sync
  created() {
    eventBus.$on('ageWasEdit', (age) => {
      console.log('Parent Edit Age Created Methid');
      this.age = age
    });
  }
}
</script>

<style scoped>
  div {
    background-color: lightblue;
  }
</style>
