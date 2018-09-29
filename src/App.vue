<template>
  <div class="container">
    <header>
      <h1 class="heading">{{ title }}</h1>
    </header>
    <main>
      <h2>What are dynamic components?</h2>
      <p>Dynamic components are a vue js tool so we can dynamically change which component is displayed in a browser in a particular place in a template</p>
      <ul class="nav">
        <li v-for="item in components"><a href="#" v-on:click="component = item.name">{{ item.title }}</a></li>
      </ul>
      <keep-alive>
        <component v-bind:is="component"></component>
      </keep-alive>
      <ul>
        <li v-for="link in links"><a v-bind:href="link.src">{{ link.title }}</a></li>
      </ul>
    </main>
  </div>
</template>

<script>
import formContact from './components/form-contact.vue'
import formLogin from './components/form-login.vue'
import home from './components/home.vue'

export default {
  components: {
    formContact: formContact,
    formLogin: formLogin,
    home: home,
  },
  data() {
    return {
      title: 'Welcome to Vue Dynamic Components',
      component: 'home',
      links: [
        {src: 'https://planeswalker1.github.io/', title: 'My Website'},
        {src: 'https://colorlessenergy.github.io/', title: 'Cool Website'},
        {src: 'https://github.com/planeswalker1', title: 'My Github'},
        {src: 'https://github.com/colorlessenergy', title: 'Cool Github'},
      ],
      components: [
        {name: 'home', title: 'Home component'},
        {name: 'formContact', title: 'Login component'},
        {name: 'formLogin', title: 'Contact component'},
      ],
    };
  }
}
</script>

<style>
  html {
    box-sizing: border-box;
  }

  *,
  *:before,
  *:after {
    box-sizing: inherit;
  }

  body {
    font-family: sans-serif;
    line-height: 1.5;
    margin: 0;
  }

  .container {
    margin: 0 auto;
    max-width: 1360px;
  }
</style>
