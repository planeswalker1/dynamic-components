<template>
  <div>
    <form class="form" v-on:submit.prevent="onSubmit">
      <div class="form__header">
        <h3>Login Form</h3>
        <p>Enter your details to login</p>
      </div>
      <div class="form__fields">
        <div>
          <label for="username">Username: </label>
          <input id="username" type="text" placeholder="username" required>
        </div>
        <div>
          <label for="password">Password: </label>
          <input id="password" type="password" placeholder="password" required>
        </div>
      </div>
      <div class="form__controls">
        <button v-on:click="onSubmit">Submit</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data () {
    return {

    };
  },
  methods: {
    onSubmit: function (event) {
      event.preventDefault();
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
