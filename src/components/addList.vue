<template>
    <div class="list-ele">
        <div
        class="list-cont"
        v-bind:class="{doneC : done}"
        @click="done=!done"
        > 
        {{ iAdd }}
    </div>
        <button class="close" @click="$emit('rData',index);">-</button>
    </div>
</template>
<script>
export default{
    name:'addList',
    props:['iAdd','index'],
    data(){
        return{
            done: false
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