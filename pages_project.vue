<template>
    <div>
        <div class="container">
            <nevtop></nevtop>
            <div class="page">
                
                <div class="left-page">
                    <div class="img-left">
                        ss
                    </div>
                </div>

                <div class="right-page">
            
                </div>


            </div>

        </div>
    </div>
</template>

<script>
import nevtop from '@/components/nev-top.vue'

export default {
    components:{
        nevtop
    }
}
</script>

<style lang="scss" scope>

.container{
    width: 100vw;
    height: 100vh;
    .page{
        width: 100%;
        height: 100%;
        background-color: aqua;
        padding-top: 60px;
    }
}

// .left-page{
//     width: 70%;
//     height: 100%;
//     .img-left{
//         background-image: url('../assets/tree.jpg');
//         // width: cover;
//         // height: cover;

//     }
// }    
</style>