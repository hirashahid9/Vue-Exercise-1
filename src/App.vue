<template>
  <div id="app">
    <h1 class="pb-10 text-4xl font-bold">Vue Exercise 1</h1>
    <h3 class="pb-3 text-xl font-bold">Please Select an Option</h3>
    <DropDown :options=options  @show-option="showselected" /><br><br>
    Selected id: {{selected}}
  </div>
</template>

<script>
import DropDown from './components/DropDown.vue'

export default {
  name: 'App',
  components: {
    DropDown
  },
  data(){
    return{
      m: "Welcome",
      selected: '',
      options: [
          {
              id: 1,
              title: "Ruby on Rails"
          },
          {
            id: 2,
            title: "Vue js"
        },
        {
            id: 3,
            title: "Tailwind Css"
        },
        {
            id: 4,
            title: "Node js"
        }
      ],
    }
  },
  methods: {
        showselected: function(value){
            console.log(value);
            this.selected=value.id;
        }
    }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
