<template>
  <div>
    <addBar @allData="addList($event)"></addBar>
   <div class="list-container">
        <addList 
        @rData="rList($event)" 
        v-for="(todo,index) in todoList" 
        :key="index" 
        :iAdd="todo" :index="index"></addList>
    </div>

  </div>
</template>

<script>
import addBar from './components/addBar.vue';
import addList from './components/addList.vue';

export default {
  name: 'App',
  components: {
    addBar,
    addList
  
  },
  data(){
    return{
      todoList:[]
    }
  },
  methods:{
  addList(idata){
      this.todoList.push(idata);
  },
  rList(rData){
    this.todoList.splice(rData,1);
  }
},
mounted(){
  if(localStorage.todoList){
    this.todoList=JSON.parse(localStorage.todoList);
  }

},
watch:{
  todoList:{
    handler(newList){
        localStorage.todoList=JSON.stringify(newList);
      },
      deep:true

    }
  }
}



</script>

<style>
body{
  margin:0px;
  width:auto;
}
.list-container{
    display:flex;
    flex-direction:column;
    min-height:500px;
    padding:10px;
    border: 5px solid black;
    
}

@media only screen and (min-width:768px){
  body{
    padding:90px;
  }
}

</style>
