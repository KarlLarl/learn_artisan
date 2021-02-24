<template>
<div >
  <div class="paper" >
      <div class="images" >
          <div>
              <label class="txts" >{{cardname}}</label>
              <img class="photo" :src="background">
              <i class="material-icons" >create</i>

            </div>   
        </div> 
        <div class="dropdata" style="margin-left: 25px">
            <img class="accounts" :src="image">
            <label class="txtpeople">{{People}}</label><br>
            <lable class="txtstatus">{{Statuss}}</lable>   
        </div>
    </div>
</div>

</template>

<script>
export default {
    props:[
        'cardname','People','classphoto','image','background','Statuss'
    ],
    data(){
        return{
            
        }

    }
}

</script>


<style>
.paper {
  height: 200px;
  background-color: white;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  margin-bottom: 25px;
  margin-top: 25px;
  margin-left: 25px;
  border-radius: 15px;


}
.container{
  margin-left: 25px;

}

.txts{
  font-weight: bold;
  color: rgb(255, 255, 255) ;
  position:absolute;
  margin-left: 20px;
  margin-top: 25px;
  font-size: 20px;
 
}


.accounts{
  float: left;
  width: 40px;
  border-radius: 50%;
}
.txtpeople{
  margin-left: 10px;
  padding: 10px 20px;
  font-weight: bold;
}
.txtstatus{
  margin-left: 10px;
  padding: 10px 20px;
  font-size: 10px;

}
.photo {
  display: flex;
  width: 100%;

}

.dropdata{
  margin-top: 10px;
}
.images{
  position: relative;
  width: 250px;
}
.material-icons{
  position:absolute;
  top:10px;
  right: 15px;
  width: 15px;
  color: white;


}
</style>