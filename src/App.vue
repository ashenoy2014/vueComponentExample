<template>
  
  <div class="appt">
    <button  class="br" v-on:click="toggleTheme" aria-label="Toggle themes">
      <span v-if="this.theme == 'darkMode'"> Light Mode</span>
      <span v-else> Dark Mode</span>     
    </button>
    {{ message }}
    <compx > </compx>
    <compy> </compy>
  </div>
</template>

<script>
import comp2 from './comp2.vue'
import comp3 from './comp3.vue'

export default {
  data: function() {
    return {
      message: 'Hello World5',
      theme: '',
    };
  },
  components: {
    'compx': comp2,
    'compy': comp3
  },

  mounted() {
        let localTheme = localStorage.getItem('theme'); //gets stored theme value if any
        document.documentElement.setAttribute('data-theme', localTheme); // updates the data-theme attribute
  },

  methods: {
    toggleTheme: function() {
              this.theme = this.theme == 'darkMode' ? '' : 'darkMode'; //toggles theme value
              document.documentElement.setAttribute('data-theme', this.theme); // updates the data-theme attribute
              localStorage.setItem('theme', this.theme); // stores theme value in local storage
    },

  },

  

};
</script>

<style>
/* main.css */
:root {
    /* Variables for default theme (light-mode) */
    --background-color: white;
    --text-color: black;  
}

[data-theme="darkMode"] {
    /* Variables for dark mode */
    --background-color: black;
    --text-color: white;   
}
.appt {
  font-size: 12px;
  font-family: 'Roboto', sans-serif;
  /*color: blue;*/

  background-color: var(--background-color);
    color: var(--text-color);
}

.br {
  border-top-left-radius: 12px;
  border-top-right-radius: 12px;
  border-bottom-left-radius: 12px;
        border-bottom-right-radius: 12px;
        border: 1px solid #ccc;
        cursor: pointer;
        background: #f0f0f0;

}
</style>
