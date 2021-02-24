<template>

    <div class="animation-show">
        <div class="txt-title">{{title}}</div>
        <form v-if="path === 'register'">
            <div  class="txt-word">
                <p>Firstname</p>
            </div>
            <div class="input-text">
                <input type="text" required/>
            </div>
            <div class="txt-word">
                <p>Lastname</p>
            </div>
            <div class="input-text">
                <input type="text" required/>
            </div>
            <div class="txt-word">
                <p>Phone Number</p>
            </div>
            <div class="input-text">
                <input type="text" required/>
            </div>
            <div class="txt-word">
                <p>E-mail</p>
            </div>
            <div class="input-text">
                <input type="email" required/>
            </div>
            <div class="txt-word">
                <p>Password</p>
            </div>
            <div class="input-text">
                <input type="password" required/>
            </div>
            <div class="txt-word">
                <p>Confirm password</p>
            </div>
            <div class="input-text" >
                <input type="password" required/>
            </div>

            <div class="btn-form">
                <button class="btn-submit" type="submit">REGISTER</button>
            </div>  
        </form>

        <form v-if="path === 'index'">
            <div class="txt-word" style="margin-top: 50px;">
                <p>E-mail</p>
            </div>
            <div class="input-text">
                <input type="email" v-model="formInput.mail"/>
            </div>
            <div class="txt-word">
                <p>Password</p>
            </div>
            <div class="input-text">
                <input type="password" v-model="formInput.password"/>
            </div>
            <div class="txt-word">
                <nuxt-link to="/forget">
                    <button class="text-forget-btn">* Forget Password</button>
                </nuxt-link>
            </div>

            <div class="btn-form" style="margin-top: 80px;">
                <button class="btn-submit" type="button" >LOGIN</button>
            </div>  
        </form>

        <form v-if="path === 'forget'">

            <div class="forget-detail">
                <label>Enter your email address. You will receive an email. With your new password.</label>
            </div>

            <div class="txt-word" style="margin-bottom: 10px;">
                <label style="color: #fa5d01; margin-right:2px;">*</label><label>Email address</label>
            </div>
            <div class="input-text">
                <input type="email" required/>
            </div>

            <div class="btn-form" style="margin-top: 50px;">
                <button class="btn-submit" type="submit">SEND RECOVERY EMAIL</button>
            </div>  

            <div class="btn-form">
                <nuxt-link to="/"><button class="btnToIndex" >BACK TO LOGIN</button></nuxt-link>
            </div>
        </form>
    </div>
    
</template>

<script>

export default {

    data(){
        return{
            textBtn: 'TEST',
            title: 'Title',
            path: null,

            formInput: {
                firstname: '',
                lastname: '',
                phone: '',
                mail: '',
                password: '',
                conPassword: ''
            }
        }
    },
    mounted(){
        this.path = this.$route.name

        switch(this.path){
            case 'index' : this.title = 'LOGIN'; break;
            case 'register' : this.title = 'REGISTER'; break;
            case 'forget' : this.title = 'FORGET PASSWORD'; break;
        }

    },
    methods:{
        onSubmit(){
            
        }
    }
    
}

</script>

<style lang="scss">

    $fontColor: #5f5f5f;
    $fullWidth: 100%;
    $heightInput: 35px; 
    $bgInput: #e9e9e9;
    $bgDefault: #fa5d01;

    .txt-title,.txt-word,.input-text,.btn-form{
        width: $fullWidth;
    }

    .txt-title{
        margin-bottom: 15px;
        font-size: 30px;
        font-weight: 600;
        color: $fontColor;
    }
    
    .txt-word{
        margin-top: 15px;
        color: $fontColor;
        margin-bottom: 2px;
        .text-forget-btn{
            color: $bgDefault;
            font-size: 12px;
            font-weight: 300;
            background-color: transparent;
            border: none;
            outline: none;
        }
    }

    .input-text{
        input{
            width: $fullWidth;
            height: $heightInput;
            border-radius: 5px;
            border: none;
            outline: none;
            background-color: $bgInput;
            padding: 0px 5%;
        }
    }

    .btn-form{
        margin-top: 40px;
        display: flex;
        justify-content: center;

        .btn-submit{
            width: $fullWidth;
            height: ($heightInput+5);
            background-color: $bgDefault;
            color: #fff;
            border: none;
            border-radius: 5px;
            font-size: 16px;
        }
        .btn-submit:hover{
            background-color: rgba(250, 93, 1, 0.7);
        }

        .btnToIndex{
            background-color: transparent;
            border: none;
            outline: none;
            font-weight: 300;
        }
        .btnToIndex:hover{
            color: $bgDefault;
        }
    }

    .forget-detail{
        margin-bottom: 50px;
        label{
            font-size: 14px;
            font-weight: 200;
            line-height: 1px;
        }
    }


    .animation-show{
        animation-name: myanination;
        animation-duration: 1.5s;
    }

    @keyframes myanination {
          0% {
            opacity: 0;
            margin-top: -500px;
          }
          100%{
            opacity: 1;
            margin-top: 0px;
          }
        }
</style>