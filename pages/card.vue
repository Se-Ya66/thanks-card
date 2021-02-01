<template>
    <div class="space1">
        <v-container>
            <div class="space2">
                <v-container>
                        <div>
                            <h2 class="page-title">Thanks Card</h2>
                            <p class="explan">ダウンロードボタンよりサンクスカードをお受け取りください。<br>ダウンロードが開始されない場合はカードを長押しして保存してください。</p>
                        </div>
                        <div>
                            <div class="img-wrapper">
                                <img src="../static/thankscard.png" class="thankscard">
                            </div>
                            <div class="button pat1">
                                <a href="https://thankscard-provider.netlify.app/thankscard.png" class="link" download="thankscard.png">
                                    <span class="link">
                                        Download
                                    </span>
                                </a>
                            </div>
                        </div>
                    
                </v-container>
            </div>
        </v-container>
    </div>
</template>

<script>
export default {
    data(){
        return{
        }
    }
}
</script>

<style>
.space1{
    background: #eef2f3;  
    width: 100%;
    height:100vh;
    position:relative;
    padding:20px 0;
}
.space2{
    font-size: 62.5%;
    background-color: white;
    width: 80%;
    text-align: center;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translateY(-50%) translateX(-50%);
}
.img-wrapper{
    width: 100%;
    text-align: center;
    margin: 0 auto;
}
.thankscard{
    width: 20%;
    margin-bottom:20px;
}
.page-title{
    text-align: center;
    font-family: 'Great Vibes', cursive;
    color:rgb(240, 217, 159);
    margin-bottom: 20px;
    font-size:3rem;
}
.explan{
    font-family: 'Noto Serif JP', serif;
    font-size:1rem;
}
.button{
    text-align: center;
    margin: 0 auto;
    color:rgb(240, 217, 159);
    border:solid 1px rgb(240, 217, 159);
    position: relative;
    cursor: pointer;
    width:100px;
    height: 50px;
    line-height: 50px;
    transition: all 0.3s;
    font-family: 'Source Sans Pro', sans-serif;
    font-weight: 600;
    font-style: italic;
    font-size:15px;
}
.button:hover{
    color:white;
    border:solid 1px rgb(240, 217, 159);
    background-color: rgb(240, 217, 159);
}
.button span{
    z-index:3;
    position: absolute;
}
.one{
    position: absolute;
    top:50%;
    left: 50%;
    transform:translate(-50%, -50%);
    display: block;
    width: 100%;
    }
.one:hover{
    color:white;
}
.button span:hover{
    z-index:3;
    color:white;
}
.button::after{
    content: '';
    position: absolute;
    transition: all 0.3s;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 100%;
    transform: scale(0.1, 0.1);
    z-index:1;
}
.button:hover::after {
    background-color: rgb(240, 217, 159);
    transform: scale(1, 1);
    z-index:1;
    color:white;
}
.pat1{
    border:solid 1px rgb(240, 217, 159);
    color:white;
}
.pat1:hover{
    color:white;
    border:solid 1px white;
    background-color: rgb(240, 217, 159);
}
.pat1:hover::after {
    background-color: rgb(240, 217, 159);
    color:white;
}
.link{
    color:rgb(240, 217, 159);
    text-decoration: none;
    display: block;
    width: 100%;
    position: absolute;
    top:50%;
    left: 50%;
    transform:translate(-50%, -50%);
    display: block;
    width: 100%;
    z-index:3;
}
.link:hover{
    color:white;
    text-decoration: none;
    display: block;
    width: 100%;
}
@media (min-width:1024px){
    .space2{
        padding-top:20px;
    }
    .explan{
        width:70%;
        margin: 0 auto;
    }
    .main{
        margin-top:50px;
    }
    .sub{
        display:none;
    }
}
@media (min-width:768px) and ( max-width:1023px) {
    .sub{
        display:none;
    }
}
@media (max-width: 767px){
    .button{
        height: 30px;
        line-height: 30px;
    }
    .explan{
        font-family: 'Noto Serif JP', serif;
        font-size:0.8rem;
    }
    .thankscard{
        margin-bottom:20px;
        width:40%;
    }
}
</style>