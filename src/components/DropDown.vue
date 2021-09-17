<template>
  <div class="w-40 m-auto shadow-xl">
    <button @click="visible=!visible" class="w-40 bg-gray-200 rounded-t hover:bg hover:bg-gray-300">{{selected}}</button>
    <div v-if="visible" class="w-40 px-1 pt-1 m-auto bg-white rounded-lg ">
      <div v-for="item in options" :key="item.id">
      <a href="#" @click="changeSelected(item)" class="block border-b-2 bg-gray-150 hover:bg-gray-200">{{item.title}}</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DropDown',
  props: {
    options: Array
  },
  data()
  {
    return {
      visible: false,
      selected: 'Select an option'
    }
  },
  methods: {
        changeSelected: function(value){
          this.selected=value.title
          this.visible=false
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
