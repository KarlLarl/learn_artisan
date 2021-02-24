<template>
    <div align="center">
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
import name from '@/json/nameloop'
export default {
    data(){
        return{
            name
            
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