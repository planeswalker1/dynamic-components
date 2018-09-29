<template>
  <div>
    <form class="form" v-on:submit.prevent="onSubmit">
      <div class="form__header">
        <h3>Contact Form</h3>
        <p>Fill in this form to contact us</p>
      </div>
      <div class="form__fields">
        <div>
          <label for="username">Username: </label>
          <input id="username" type="text" placeholder="username" required>
        </div>
        <div>
          <label for="text">Your Message: </label>
          <textarea id="text" cols="30" rows="8"></textarea>
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
