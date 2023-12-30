<script>
import Greetings from './components/Greetings.vue'

export default{
  components:{
    Greetings
  },
  methods:{
    // Heart
    hovers: function(){
      document.getElementById('heart').classList.remove('abc')
      document.getElementById('heart').classList.add('heart')
    },
    hoversLeave: function (){
      document.getElementById('heart').classList.add('abc')
      document.getElementById('heart').classList.remove('heart')
    },
    // Music
    hovers2: function(){
      document.getElementById('music').classList.remove('abc')
      document.getElementById('music').classList.add('music')
    },
    hovers2Leave: function(){
      document.getElementById('music').classList.add('abc')
      document.getElementById('music').classList.remove('music')
    },
    // Happy
    hovers3: function(){
      document.getElementById('happy').classList.remove('abc')
      document.getElementById('happy').classList.add('happy')
    },

    clicks: function (){
      this.show = true
      document.getElementById('card').classList.add('click')
      document.getElementById('heart').classList.remove('abc')
      document.getElementById('heart').classList.add('asdc')
      
    },
    clicks2: function (){
      this.show2 = true
      document.getElementById('card2').classList.add('click')
      document.getElementById('music').classList.remove('abc')
      document.getElementById('music').classList.add('zxc')
    },
  },
  data(){
    return {
      show: false,
      show2: false
    }
  }
}
</script>

<template>
  <!-- <Greetings/> -->
  <div v-if="show == true" class="happy-wrapper" v-on:click="show = false">
    <div class="grid">
      <div>
        <img src="./assets/me.jpg" alt="">
      </div>
      <div style="background-color: rgb(181, 255, 181); border-radius: 8px; padding: 1rem 1rem 0 1rem; position: relative;">
        <p style="color: rgb(63, 63, 63);">
          Happy Anniversary sayang! <br>
          ga kerasa ya udah 1 tahun aja, susah seneng kita hadepin bareng-bareng.
          Maaf yaa aku blm bisa ngasih apa-apa, belum jadi yang terbaik juga buat kamu,
          walaupun banyak ributnya, kita sama-sama egois juga, tapi aku tetep sayang kamu.
          jangan selingkuh ya ajg, kamu harus tetep sama aku, buat kedepannya semoga kita
          jadi pribadi yang lebih baik lagi, buat keluarga, lingkungan, dan orang-orang di
          sekitar kamu. Maaf ya aku cuma bisa buatin beginian doang hehe, i love u,
          Happy new year sayang!
        </p>
        <div class="clock">17.05 <i class="fa-solid fa-check"></i></div>
        <i class="fa-solid fa-caret-up"></i>
      </div>
    </div>
  </div>
  <div v-if="show2 == true" class="music-wrapper">
    <div class="music-card">
      <div class="img">
        <img src="./assets/qr.png" alt="">
      </div>
      <p>Scan aku bub</p>
      <i class="fa-solid fa-x" v-on:click="show2 = false"></i>
    </div>
  </div>
  <div class="wrapper">
    <div v-on:mouseenter="hovers()" v-on:mouseleave="hoversLeave()" v-on:click="clicks()" class="card" id="card">
      <!-- <i v-if="hover == false" class="fa-solid fa-heart abc" id="heart"></i> -->
      <i class="fa-solid fa-heart" id="heart"></i>
    </div>
    <div v-on:mouseenter="hovers2()" v-on:mouseleave="hovers2Leave()" v-on:click="clicks2();" class="card" id="card2">
      <i class="fa-solid fa-music" id="music"></i>
    </div>
  </div>
</template>

<style scoped>

  .happy-wrapper .grid{
    position: relative;
    display: grid;
    column-gap: 1.5rem;
    padding: 0;
    grid-template-columns: 13% 87%;
    /* background-color: white; */
    width: 30rem;
  }

  .grid div i{
    position: absolute;
    transform: rotate(-90deg);
    color: rgb(181, 255, 181);
    font-size: 2rem;
    top: -1px;
    left: -10px;
  }

  .grid div{
    position: relative;
    color: rgb(63, 63, 63);
  }

  .grid div .clock{
    text-align: right;
    margin: 0 0 10px;
    font-size: 14px;
  }

  .grid div .clock i{
    position: relative;
    top: 0;
    left: 0;
    font-size: 15px;
    color: gray;
    transform: rotate(0deg);
    margin-left: 3px;
  }

  .grid div img{
    width: 100%;
    border-radius: 50%;
    top: -20px;
    position: absolute;
  }

  .music-wrapper, .happy-wrapper{
    position: absolute;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 100vh;
    background-color: rgba(0, 0, 0, 0.137);
  }

  .music-wrapper .music-card{
    position: relative;
    background-color: white;
    text-align: center;
    padding: 10px;
    width: 20rem;
    border-radius: 8px;
  }

  .music-wrapper .music-card i{
    position: absolute;
    cursor: pointer;
    color: white;
    top: -1rem;
    right: -1rem;
    padding: 10px 13px;
    border-radius: 50%;
    background-color: rgb(231, 108, 231);
  }

  .music-wrapper .music-card p{
    font-size: 18px;
  }

  .music-wrapper .music-card .img img{
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  .card{
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    background-color: rgb(27, 27, 27);
    padding: 20px;
    margin: 0 10px;
    width: 12rem;
    height: 20rem;
    box-shadow: 1px 1px 5px rgb(19, 19, 19), -1px -1px 5px rgb(19, 19, 19);
    font-size: 4rem;
  }

   .card:hover, .click{
    width: 15rem;
    height: 22rem;
    font-size: 5rem;
  }

  .heart, .asdc{
    text-shadow: 1px 1px 6px rgb(255, 87, 87), -1px -1px 6px rgb(255, 87, 87);
    color: rgb(255, 87, 87);
  }

  .music, .zxc{
    text-shadow: 1px 1px 6px rgb(87, 255, 157), -1px -1px 6px rgb(87, 255, 157);
    color: rgb(87, 255, 157);
  }

  .happy, .prikitiw{
    text-shadow: 1px 1px 6px rgb(240, 255, 100), -1px -1px 6px rgb(240, 255, 100);
    color: rgb(240, 255, 100);
  }

</style>
