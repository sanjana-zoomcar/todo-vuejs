<template>
    <div class="list-ele">
        <button
        class="list-cont"
        v-bind:class="{doneC : done}"
        @click="done=!done"
        > 
            {{ iAdd }}
    </button>
        <button class="close" @click="delTask">-</button>
    </div>
</template>
<script>
export default{
    name:'addList',
    props:['iAdd'],
    data(){
        return{
            done: false
        }

    },
    methods:{
        delTask(){
            console.log("BUTTON CLICK")
            let close = document.getElementsByClassName("close");
            let i;
            for (i = 0; i < close.length; i++) {
                close[i].onclick = function() {
                    console.log("BUTTON CLICK this :",i)
                    let div2 = this.parentElement;
                    console.log(div2);
                    div2.remove();
                    this.$emit('rData',this.iData);
                }
            } 
        }
    },
    mounted(){
        this.delTask();   

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
    background-color: white;
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
.doneC{
    text-align: center;
    border:2px solid black;
    padding:2px;
    flex-basis:80%;
    background-color: lightgray;
    text-decoration: line-through;
}
</style>