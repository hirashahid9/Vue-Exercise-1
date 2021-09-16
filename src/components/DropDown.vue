<template>
  <div class="hello">
    <h1>Vue Exercise 1</h1>
    <h2>Please Select an Option</h2>
    <select @change="ChangeItem($event.target.value)" >
      <option v-for="item in options" :key="item.id" :value="item.id">
        {{ item.title }}
      </option>
    </select>
  </div>
</template>

<script>
export default {
  name: 'DropDown',
  props: {
    msg: String,
    options: Array
  },
  
  methods: {
        ChangeItem: function(value){
          console.log(value)
            this.$emit('show-option',value)
        }
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
