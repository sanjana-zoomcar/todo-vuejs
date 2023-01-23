<template>
    <div class="add-bar">
        <input class="add-input" v-model="iData" @keyup.enter="addToList "  >
        <button class="add-button" @click="addToList">+</button>
    </div>

</template>
<script>
export default{
    name:'addBar',
    data(){
        return{
            iData: ''
        }
    }, 
    methods:{
        addToList: function(){
            if(this.iData.length>=1){
            this.$emit('allData',this.iData);
            this.iData='';
            
            }
            
        }

    }
}
</script>
<style>
.add-bar{
    max-width:100%;
    padding:10px;
    display:flex;
    justify-content:center;
    border: 5px solid black;
    
}
.add-input{
    border: 2px solid black;
    height:20px;
    flex-basis:80%;
}
.add-button{
    border: 2px solid black;
    flex-basis:10%;
    color:white;
    background-color: black;
}

.add-button:hover{
    color:black;
    background-color: white;
}
</style>



