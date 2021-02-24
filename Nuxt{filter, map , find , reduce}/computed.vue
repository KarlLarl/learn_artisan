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
        
        <table style="width:50%">
            <thead>
                <tr>
                    <th>Name</th>
                    <th>Age</th>
                    <th>Sex</th>
                </tr>
            </thead>
        <!--    Loop name age sex   -->
        <tbody align="center">
            <tr v-for="(index) in messages" :key="index">
                <td>{{index.firstname}}</td>
                <td>{{index.age}}</td>
                <td>{{index.sex}}</td>


            </tr>

        </tbody>
        </table>
        <!-- Table  computed -->
        <table style="width:50%">
            <thead>
                <tr>
                    <th>อายุรวม</th>
                    <th>ชื่อคน</th>
                    <th>อายุมากกว่า 20</th>
                    <th>เปลี่ยนเพศเป็นภาษาไทย</th>
                </tr>
            </thead>
        <!--    Show Computed  -->
        <tbody align="center">
            <tr>
                <td>{{reduce}}</td>
                <td><li>{{finds}}</li></td>
                <td> {{filter}}</td>
                <td><li>{{genders}}</li></td>
            </tr>
        </tbody>
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
            this.messages.push({
                firstname:this.firstname,
                age:this.age,
                sex:this.sex})
            this.messages
        },
        del(){
            this.messages.splice(this.messages)
            this.messages
        }

    },computed:{
        filter(){
            const result = this.messages.filter((age) => {
            return age.age >= 20
            
            },0)
            return result
        },
        
        reduce(){
            const result = this.messages.reduce((sum,age) => {
            return parseInt(sum)+parseInt(age.age)
        },0)
            return result
        
        },
        finds(){
            const result = this.messages.find((firstname) => {
            return `${this.firstname}`
        })
            return result
        },
        map(){
            const result = this.messages.map((name,age,sex) => {
            return this.sex
        },0)
            return result
        }
        
    }
}
</script>









<style>
table {
  width: 100%;
  border-collapse: collapse;
}

th {
  height: 50px;
}
  

table, th, td {
  border: 1px solid black;
}
</style>