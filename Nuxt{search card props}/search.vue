<template>

  <div >
    <div>
      <ul>
        <label class="Head">Project List</label><br>
        <li class="active">Project List</li>

        <li ><div style="margin-left:100px">
          ค้นหา<input class="search-img" type="text" placeholder="Search.." v-model="search">
        </div></li>

        <li>เรียงตาม <select>
          <option>วันที่เริ่มโครงการ</option>
        </select>
        </li>
        <li><button >เพิ่ม Zone</button></li>
        <li><button >เพิ่ม Template</button></li>
        <li><button class="resets" type="submit" onclick="window.location.href='/search'" ></button></li>
        
      
      </ul>
    </div>

    <div class="flexs" >
      <card  v-for="(data,index) in Searchlist" :key="index" 
      :cardname="data.proname"
      :People="data.name"
      :image="data.image"
      :background="data.background"
      :Statuss="data.status"
      />
    </div>
        
    



 

</div>

</template>

<script>

import card from '@/components/card'


export default {
  components:{
    card
  },
  data(){
    return{
        search:'',
        listData:[
            {
                proname: 'Project for test 01',
                name: 'Melon',
                image: require('@/assets/profile02.jpg'),
                background: require('@/assets/photo02.jpg'),
                status: 'Admin',
            },
            {
                proname: 'SDLC',
                name: 'Miline',
                image: require('@/assets/profile01.jpg'),
                background: require('@/assets/photo01.jpg'),
                status: 'User'
            },
            {
                proname: 'Nuxt',
                name: 'Apple',
                image: require('@/assets/profile03.jpg'),
                background: require('@/assets/photo03.jpg'),
                status: 'Devaloper'
            },
            {
                proname: 'Design',
                name: 'Lolicon',
                image: require('@/assets/profile04.jpg'),
                background: require('@/assets/photo05.png'),
                status: 'Designer'
            },
            {
                proname: 'Empty',
                name: 'Unknow',
                image: require('@/assets/profile04.jpg'),
                background: require('@/assets/photo04.jpg'),
                status: 'User'
            },
            {
                proname: 'Empty',
                name: 'Unknow',
                image: require('@/assets/profile04.jpg'),
                background: require('@/assets/photo04.jpg'),
                status: 'User'
            },
            {
                proname: 'Empty',
                name: 'Unknow',
                image: require('@/assets/profile04.jpg'),
                background: require('@/assets/photo04.jpg'),
                status: 'User'
            }
        ]
      }
    },computed: {
      Searchlist(){
        if (this.search == ''){
          return this.listData
        }else {
          return this.listData.filter((data) =>{
          return data.proname.includes(this.search)
        })
        }
       
      }

  }
}




    

</script>

<style>
body{
  background-color: rgb(247, 247, 247)
}

ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  overflow: hidden;

}

li {
  float: left;
  margin-left: 15px;
  height: 60px;
}

input{
  margin-top: 15px;
  border-radius: 15px;
  height: 30px;
  text-align: center;
}
select{
  height: 30px;
  width: 120px;
  margin-top: 15px;
  border-radius: 8px;
}
button{
  margin-top: 10px;
  background-color: antiquewhite;
  border-radius: 5px;
  height: 40px;
  font-weight: bold;
  border: none;
  box-shadow: 0px 2px 2px 0 rgba(0, 0, 0, 0.2);
}
.search-img{
  background-image:url('../assets/search.png');
  background-position: left;
  background-size: 15px;
  background-repeat: no-repeat ;
  border-radius: 8px;
  background-position-x: 10px;
  margin-left: 10px;
}
.active{
  margin-top: 10px;
  font-weight: bold;
  font-size: 26px;
  margin-left: 25px
}
.Head{
  font-weight: normal;
  margin-left: 25px;

}
.resets{
  background-image:url('../assets/reset.png');
  background-size: 30px;
  background-repeat: no-repeat ;
  width: 50px;
  background-position: 50%
}
.flexs{
  
  display: flex;
  flex-wrap: wrap;
  justify-content:center;

}


</style>