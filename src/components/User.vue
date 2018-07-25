<template>
  <div class="component">
    <h1>The User Components</h1>
    <p>I'm An Awesome User!</p>
    <button class="btn btn-info" @click="changeName">Open Real Name</button>
    <hr>
    <div class="row">
      <div class="col-xs-12 col-sm-6">
        <appUserDetail :name="realName"></appUserDetail>
      </div>
      <div class="col-xs-12 col-sm-6">
        <appUserEdit></appUserEdit>
      </div>
    </div>
  </div>
</template>

<script>
import UserDetail from '../components/UserDetail.vue'
import UserEdit from '../components/UserEdit.vue'

export default {
  data: function() {
    return {
      realName: 'Prana Jaya'
    }
  },
  methods: {
    changeName() {
      this.realName = this.realName + ' Asmara Pratama'
    }
  },
  components: {
    appUserDetail: UserDetail,
    appUserEdit: UserEdit
  }
}
</script>

<style scoped>
  div {
    background-color: lightblue;
  }
</style>
