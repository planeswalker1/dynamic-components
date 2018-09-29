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
    padding: 40px;
    width: 60%;
  }

  /* link styles */
  ul {
    display: flex;
    flex-wrap: wrap;
    list-style-type: none;
    padding: 0;
    width: 100%;
  }

  li {
    margin-right: 10px;
  }

  a {
    background-color: transparent;
    color: #007bff;
    text-decoration: none;
  }

  a:hover {
    color: #0056b3;
    text-decoration: underline;
  }

  h1,
  form {
    margin: 0 auto;
    max-width: 600px;
  }

  .heading {
    margin: 0;
    max-width: unset;
  }

  h1 {
    margin-top: 1em;
  }

  p {
    margin-bottom: 0;
  }

  .form__header,
  .form__fields,
  .form__controls {
    padding: 5px;
  }

  /* form control styles */
  .group {
    margin-bottom: 10px;
  }

  label {
    display: inline-block;
    margin: .5em 0;
  }

  input {
    background-color: #fff;
    background-clip: padding-box;
    border: 1px solid #ced4da;
    border-radius: .25em;
    color: #495057;
    display: block;
    font-size: 1em;
    width: 300px;
    line-height: 1.5;
    padding: .375em .75em;
    transition: border-color .15s ease-in-out,box-shadow .15s ease-in-out;
  }

  input:focus {
    background-color: #fff;
    border-color: #80bdff;
    box-shadow: 0 0 0 0.2em rgba(0,123,255,.25);
    color: #495057;
    outline: 0;
  }

  textarea {
    background-clip: padding-box;
    background-color: #fff;
    border: 1px solid #ced4da;
    border-radius: .25em;
    color: #495057;
    display: block;
    line-height: 1.5;
    overflow: auto;
    padding: .375em .75em;
    resize: vertical;
    transition: border-color .15s ease-in-out,box-shadow .15s ease-in-out;
    width: 300px;
  }

  textarea:focus {
    background-color: #fff;
    border-color: #80bdff;
    box-shadow: 0 0 0 0.2em rgba(0,123,255,.25);
    color: #495057;
    outline: 0;
  }

  button {
    background-color: #007bff;
    border: 1px solid transparent;
    border-color: #007bff;
    border-radius: .25em;
    color: #fff;
    display: inline-block;
    font-size: 1em;
    font-weight: 400;
    line-height: 1.5;
    padding: .375em .75em;
    text-align: center;
    transition: color .15s ease-in-out,background-color .15s ease-in-out,border-color .15s ease-in-out,box-shadow .15s ease-in-out;
    user-select: none;
    -webkit-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    vertical-align: middle;
    white-space: nowrap;
  }

  button:hover {
    background-color: #0069d9;
    border-color: #0062cc;
    color: #fff;
    cursor: pointer;
  }

  button:focus {
    outline: 0;
    box-shadow: 0 0 0 0.2em rgba(0,123,255,.5);
  }

  @media screen and (max-width: 800px) {
    .container {
      padding: 20px;
      width: 80%;
    }
  }

  @media screen and (max-width: 500px) {
    .container {
      padding: 10px;
      width: 90%;
    }

    input,
    textarea {
      width: 100%;
    }
  }
</style>
