<template>
    <div class="wrap">
        <div class="slide-wrapper">
          <img src="../static/wed1.jpg" class="slideshow top">
          <img src="../static/wed2.jpg" class="slideshow fadeout">
          <img src="../static/wed3.jpg" class="slideshow fadeout">
        </div>
        <div class="qr-wrapper">
            <p class="message1">Thank you<br>for coming</p>
            <p class="message2">本日はお忙しい中ご出席いただき<br>誠にありがとうございました。</p>
            <img src="../static/QR.png" class="qr">
            <p class="message3">QRコードより新郎新婦からの<br>サンクスカードをお受け取り下さい。</p>
        </div>
        <div class="name">
            <div class="names">Haruki & Yuko</div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
          index: 0,
        }
    },
    mounted() {
        const images = document.getElementsByClassName('slideshow');
        this.slideshow(images);
        setInterval(() => {
        this.index = this.index < images.length - 1 ? this.index + 1 : 0;
        this.slideshow(images);
        }, 8000);
    },
    methods: {
        slideshow(images) {
        const current = images[this.index];
        const prev = images[this.index - 1] ? images[this.index - 1] : images[images.length - 1];
        current.classList.add('fadein');
        current.classList.remove('fadeout');
        prev.classList.remove('fadein');
        prev.classList.add('fadeout');
        }
    }
}
</script>

<style>
*, *::before, *::after {
  box-sizing: border-box;
  margin : 0;
  padding : 0;
}
.fadein {
    opacity: 1;
    transition: opacity 4s;
}
.fadeout {
    opacity: 0;
    transition: opacity 4s;
}

.slideshow {
    position: absolute;
    width: 100%;
    height: 100vh;
    object-fit: cover;
}
.slide-wrapper{
    width: 100%;
    height: 100vh;
    position: relative;
    z-index: 2;
    overflow: hidden;
}
.wrap{
    position: relative;
    background-color: white;
    overflow: hidden;
    height:100vh;
}
.name{
    position:absolute;
    top:0;
    left:0;
    z-index:5;
    font-family: 'Cormorant Garamond', serif;
    font-weight:300;
    text-transform: uppercase;
    margin:0;
}
.names{
    font-size: 90px;
    color:#fffff0;
    margin:0;
    line-height:1;
}
.qr-wrapper{
    position: absolute;
    bottom:2%;
    right:2%;
    background-color: #E5BD54;
    opacity:0.9;
    z-index:4;
    padding:30px;
    border-radius: 10px;
    text-align: center;
}
.message1{
    color:white;
    font-size: 50px;
    margin-top: 10px;
    font-family: 'Great Vibes', cursive;
    line-height: 1;
}
.message2{
    color:white;
    margin-top: 16px;
    font-family: 'Noto Serif JP', serif;
    font-weight: 400;
}
.message3{
    color:white;
    margin-top: 16px;
    font-family: 'Noto Serif JP', serif;
    font-size:15px;
    font-weight: 400;
}
.qr{
      width:70%;
      margin-top: 10px;
    }
@media (min-width:1024px){
    .name{
      bottom:0;
    }
}

@media (min-width:768px) and (max-width: 1023px){
    .qr-wrapper{
      padding:10px;
    }
    .names{
      font-size: 8vw;
    }
    .qr{
      width:50%;
    }
    .message1{
      font-size:30px;
    }
    .message2{
      font-size:10px;
    }
    .message3{
      font-size:10px;
    }
    .name{
      position:absolute;
      bottom:0;
    }
}

@media (max-width: 767px){
  .slideshow {
    position: absolute;
    width: 100%;
    height: 100vh;
    object-fit: cover;
  }
  .slide-wrapper{
    width: 100%;
    height: 100vh;
    position: relative;
    z-index: 2;
    overflow: hidden;
  }
  .top{
    width: 100%;
    height: 100vh;
    object-position: 30% 70%;
  }
  .qr-wrapper{
    padding:5px;
  }
  .qr{
    width:50%;
  }
  .message1{
    font-size:20px;
    line-height: 1;
  }
  .message2{
    font-size:10px;
  }
  .message3{
    font-size:10px;
  }
  .name{
    position:absolute;
    top: 0;
    left:0;
  }
.names{
    font-size: 45px;
    color:#fffff0;
}
}
</style>
