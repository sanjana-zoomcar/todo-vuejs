<template>
    <div class="list-ele">
        <div class="list-cont"><p>{{ iAdd }}</p></div>
        <button class="close" @click="delTask">-</button>
    </div>
</template>
<script>
export default{
    name:'addList',
    props:['iAdd'],
    methods:{
        delTask: function(){
        let close = document.getElementsByClassName("close");
        let i;
        for (i = 1; i < close.length; i++) {
            close[i].onclick = function() {
                var div2 = this.parentElement;
                console.log(div2);
                div2.remove();
            }
  }
    }
    
}
}
</script>
<style>
.list-ele{
   
    display:flex;
    justify-content: center;
    padding: 0px;

}
.list-cont{
    text-align: center;
    border:2px solid black;
    padding:2px;
    flex-basis:80%;
}
.close{
    border: 2px solid black;
    flex-basis:10%;
    color:white;
    background-color: black;
}
.close:hover{
    color:black;
    background-color: white;
}
p{
    margin:0px;
}
</style>


let close = document.getElementsByClassName("close");
            let i;
            for (i = 1; i < close.length; i++) {
                close[i].onclick = function() {
                    var div2 = this.parentElement;
                    
                    console.log(div2);
                    div2.remove();
                }
            } 


            console.log("BUTTON CLICK")
            console.log(this.todoList);
            let close = document.getElementsByClassName("close");
            let i;
            for (i = 0; i < close.length; i++) {
                close[i].onclick = function() {
                    console.log("BUTTON CLICK this :",i)
                    let div2 = this.parentElement;
                    console.log(div2);
                    div2.remove();
                }



                console.log("BUTTON CLICK")
            console.log(this.todoList);
            let close = document.getElementsByClassName("close");
            let i;
            for (i = 0; i < close.length; i++) {
                close[i].onclick = function() {
                    console.log("BUTTON CLICK this :",i)
                    let div2 = this.parentElement;
                    console.log(div2);
                    div2.remove();} 