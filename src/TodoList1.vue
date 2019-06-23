<template>
  <div id="app">
    <!-- <img src="./assets/logo.png">
    <HelloWorld/> -->
      <input v-model="inputValue"/>
      <button @click="handlesubmit">提交</button>
      <ul>
      <todo-item v-for="(item, index) of list" :key="index" :content="item"
      :index="index"
      @delete="handledelete"
      ></todo-item>
      </ul>
  </div>
</template>

<script>

// import HelloWorld from './components/HelloWorld'

// export default {
//   name: 'App',
//   components: {
//     HelloWorld
//   }
// }

import  TodoItem from './components/TodoItem'
export default{
  // data:function () {
  //      return { inputValue:''}
  // }

  components:{
    'todo-item':TodoItem
  },
   data () {
       return { 
         inputValue:'',
         list:[]
       
       }
  },
  methods:{
    handlesubmit(){
     this.list.push(this.inputValue)
     this.inputValue=''
    },
    handledelete (index){
      this.list.splice(index,1);
    }
  }

}


</script>

<style>
/* #app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
</style>
