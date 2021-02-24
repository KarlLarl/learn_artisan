<template>
    <div align="center">
        <h6>Show Text : {{firstname}}</h6>
        User : <input type = "text" v-model="firstname">
        <button type="input" @click="trand" >Add </button>
        <button type="input" @click="del" >Del</button>
        <ul>
            <li v-for="(arr, index) in name" :key="index">
                {{arr}}

            </li>
        </ul>


        
        
    </div>
</template>

<script>

export default {
    data(){
        return{
            firstname:'',
            name:[]

        }
    }
    ,methods: {
        trand(){
            this.name.push(this.firstname),
            this.name
               
        },
        del(){
            this.name.splice(this.firstname),
            this.name
        }
    },
    
}
</script>