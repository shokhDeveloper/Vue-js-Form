<template>
<div class="align">
    <div class="container">
    <div class="align__title">
        <h1>Ma'lumotlarni kiriting</h1>
    </div>
    <div class="align__form">
        <form class="form" v-on:submit="handleSub">
            <input  type="text" v-on:keyup='handleKey' v-bind:placeholder="placeholderString" class="form__name"      maxlength="15"  required>
            <br>
            <input type="number" v-on:keyup="handleNumber" required  class="form__number" v-bind:placeholder="placeholderString2" >
            <br>
            <button class="form__btn"> {{title}} </button>
        </form>
    </div>
</div>
</div>

</template>

<script>
export default{
        data(){
            return{
                placeholderString: "Ismingizni yozing",
                placeholderString2: "Raqamingizni kiriting ",
                title: "Submit",
                input_name: ' ',
                input_number: ' ',
                block: "block",
                names: "form__name",
                arrays:  [],
                news: null
            }  
        },
        methods:{
            handleKey(e){
            this.input_name = e.target.value.trim()
            let qiymat = this.input_name
            for(let i = 0; i<qiymat.length; i++){
            if(Number(qiymat[i]) == 0 || Number(qiymat[i])){
            let targes = e.target
            targes.className = this.block
            let btn = document.querySelector(".form__btn")
            btn.readonly = true
                    
            }else{
                let targes = e.target
                targes.className = this.names
            }
            }
            },
            handleNumber(e){
                this.input_number= e.target.value.trim()
            },
            handleSub(e){
         e.preventDefault()
                this.arrays.push(this.input_name, this.input_number)
                window.localStorage.setItem("Tokens", JSON.stringify(this.arrays))
               this.news = JSON.parse(window.localStorage.getItem("Tokens"))
          
        if(this.news.length >=2){
            console.log(this.news)
            console.log("ishladi")
        }else{
            console.log(false)
        }
        }
        }
    }
</script>

<style>
body{
    font-family: "Poppins";
    }
    .align{
        width: 100%;
        height: auto;
    }
    .align__title{
        width: 100%;
        text-align: center;
        padding-top: 4rem;
    }
    .align__form{
        width: 100%;
        display: flex;
        justify-content: center;
        padding-top: 4rem;
    }
    form{
        width: 50%;
        padding: 1rem;
        margin: 0 auto;
    }
    form input {
        width: 65%;
        margin: 0 auto ;
        padding: 0.8rem 0.5rem;
        border: 1px solid transparent;
        outline: 3px solid transparent;
        transition: all 0.5s ease;
        border-radius: 10px;
        border: 1px solid rgba(128, 128, 128, 0.323);
    }
    .form__name:not(:placeholder-shown):valid{
        background-image: url("../../Images/pngegg.png");
        background-position: calc(95%);
        background-size: 50px;
        background-repeat: no-repeat;
    }
    .form__number:not(:placeholder-shown):valid{
        background-image: url("../../Images/pngegg.png");
        background-position: calc(90%);
        background-size: 50px;
        background-repeat: no-repeat;
    }
    .form__number:not(:placeholder-shown):invalid{
        background: url("../../Images/pngwing.com.png");
        background-position: calc(85%);
        background-size: 30px;
        background-repeat: no-repeat;
        outline: 3px solid crimson;
    }
    .block{
        display: block;
    }
    .block:not(:placeholder-shown){
        background: url("../../Images/pngwing.com.png");
        background-position: calc(85%);
        background-size: 30px;
        background-repeat: no-repeat;
        outline: 3px solid crimson;
    }
    form input:focus{
        outline: 3px solid rgba(18, 209, 62, 0.588);
    }
    form button{
        width: 50%;
        margin: 0 auto;
        padding: 0.8rem 1rem;
        border: 1px solid transparent;
        background: black;
        color: #fff;
        font-size: 18px;
        border-radius: 10px;
        transition: 0.5s ease;
        font-family: "Poppins";
        letter-spacing: 1px;
    }
    form button:active{
        background: #fff;
        border: 1px solid rgba(0, 0, 0, 0.267);
        color: #000;
    }
    form button:hover{
        background: #fff;
        border: 1px solid rgba(0, 0, 0, 0.267);
        color: #000;
    }
    input{
        display: block;
        font-size: 30px;
        
    }
    input::placeholder{
        font-size: 17px;
        letter-spacing: 1px;
        font-family: "Poppins";
    }
    button{
        display: block;
    }
    @media only screen and (max-width:1115px){
        .container{
            max-width: 800px;
        }
        form input {
        width: 100%;
        margin: 0 auto ;
        padding: 0.8rem 0.5rem;
        border: 1px solid transparent;
        outline: 3px solid transparent;
        transition: all 0.5s ease;
        border-radius: 10px;
        border: 1px solid rgba(128, 128, 128, 0.323);
        font-size: 18px;
        font-family: "Poppins";
    }
    .form__name:not(:placeholder-shown):valid{
        background-image: url("../../Images/pngegg.png");
        background-position: calc(95%);
        background-size: 30px;
        background-repeat: no-repeat;
    }
    .form__number:not(:placeholder-shown):valid{
        background-image: url("../../Images/pngegg.png");
        background-position: calc(90%);
        background-size: 30px;
        background-repeat: no-repeat;
    }
    .form__number:not(:placeholder-shown):invalid{
        background: url("../../Images/pngwing.com.png");
        background-position: calc(85%);
        background-size: 25px;
        background-repeat: no-repeat;
        outline: 3px solid crimson;
    }
    .block{
        display: block;
    }
    .block:not(:placeholder-shown){
        background: url("../../Images/pngwing.com.png");
        background-position: calc(85%);
        background-size: 25px;
        background-repeat: no-repeat;
        outline: 3px solid crimson;
    }
    }
    @media only screen and (max-width:867px){
        .container{
            max-width: 800px;
        }
        form input {
        width: 100%;
        margin: 0 auto ;
        padding: 0.8rem 0.5rem;
        border: 1px solid transparent;
        outline: 3px solid transparent;
        transition: all 0.5s ease;
        border-radius: 10px;
        border: 1px solid rgba(128, 128, 128, 0.323);
        font-size: 18px;
        font-family: "Poppins";
    }
    .form__name:not(:placeholder-shown):valid{
        background-image: url("../../Images/pngegg.png");
        background-position: calc(95%);
        background-size: 30px;
        background-repeat: no-repeat;
    }
    .form__number:not(:placeholder-shown):valid{
        background-image: url("../../Images/pngegg.png");
        background-position: calc(90%);
        background-size: 30px;
        background-repeat: no-repeat;
    }
    .form__number:not(:placeholder-shown):invalid{
        background: url("../../Images/pngwing.com.png");
        background-position: calc(85%);
        background-size: 25px;
        background-repeat: no-repeat;
        outline: 3px solid crimson;
    }
    .block{
        display: block;
    }
    .block:not(:placeholder-shown){
        background: url("../../Images/pngwing.com.png");
        background-position: calc(85%);
        background-size: 25px;
        background-repeat: no-repeat;
        outline: 3px solid crimson;
    }
    @media only screen and (max-width: 730px){
        .container{
            max-width: 680px;
        }
    }
    @media only screen and (max-width: 630px){
        .container{
            max-width: 580px;
        }
        form{
        width: 70%;
        padding: 1rem;
        margin: 0 auto;
    }
    form input{
        width: 80%;
    }
    }
    @media only screen and (max-width: 555px){
        .container{
            max-width: 480px;
        }
        form{
        width: 70%;
        padding: 1rem;
        margin: 0 auto;
    }
    .block:not(:placeholder-shown){
        background-position: calc(95%);
    }
    .form__number:not(:placeholder-shown):invalid{
        background-position: 90%;
    }
    form input{
        width: 95%;
    }
    }
    @media only screen and (max-width: 470px){
       .container{
        max-width: 400px;
       }
        form{
        width: 80%;
        padding: 1rem;
        margin: 0 auto;
    }
    form input{
        width: 100%;
    }
    .block:not(:placeholder-shown){
        background-position: calc(95%);
    }
    .form__number:not(:placeholder-shown):invalid{
        background-position: 90%;
    }   
    }
    @media only  screen and (max-width:396px) {
        .container{
            max-width: 350px;
        }
        .align__title h1{
            font-size: 30px;
        }
        form{
        width: 90%;
        padding: 1rem;
        margin: 0 auto;
    }
    form input{
        width: 95%;
    }
    .block:not(:placeholder-shown){
        background-position: calc(95%);
    }
    .form__number:not(:placeholder-shown):invalid{
        background-position: 90%;
    }   
    }
    @media only screen and (max-width: 340px) {
        .container{
            max-width: 300px;
        }
        .align__title h1{
            font-size: 24px;
        }
        .block:not(:placeholder-shown){
        background-position: calc(95%);
    }
    .form__number:not(:placeholder-shown):invalid{
        background-position: 90%;
    }
        form{
        width: 100%;
        padding: 1rem;
        margin: 0 auto;
    }
    form input{
        width: 100%;
    }   
        
    }
}
</style>