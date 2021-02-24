<template>
    <div align="center">
        <h6>Text : {{firstname}}</h6>
        <h6>Age : {{age}}</h6>
        <h6>Sex : {{sex}}</h6>
        
        User : <input type = "text" v-model="firstname"><br>
        Age : <input type = "text" v-model="age"><br>
        <input type="radio" name="gender" value="male" v-model="sex"> Male
        <input type="radio" name="gender" value="female" v-model="sex" > Female<br>
        <button type="input" @click="add">Add</button>
        <button type="input" @click="del">Del</button>
        <ul>
            <li v-for="(arr, index) in messages" :key="index">
                {{arr}}


            </li>
        </ul>
        <table>
            <tr>
                <th>AGE</th>
                <th>NAME</th>
                <th>20 PLUS</th>
                <th>THAI</th>
            </tr>
            <tr>
                <td>{{ages}}</td>
                <td>{{names}}</td>
                <td></td>
                <td></td>
            </tr>


        </table>


      
    </div>
    
</template>
<script>

export default {
    data(){
        return{
            firstname:'',
            age:'',
            sex:'',
            messages:[]
        }   
    },methods: {
        add(){
            this.messages.push(this.firstname,this.age,this.sex)
            this.messages
        },
        del(){
            this.messages.splice(this.messages)
            this.messages
        }

    },computed:{
        ages(){
            const ages = this.messages.reduce((sum,age) => {
            return parseInt(age.age)+parseInt(sum.age)
            },0)
            return ages
        },
        names(){
            const names = this.messages.find((name) => {
                return this.messages.firstname
            },0)
                return names
        }
    }
    
}
</script>