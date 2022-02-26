<template>
  <div class="container">
    <div>
      <h1>Geri Sayım Sayacı</h1>
      <input type="text" v-model="timer" placeholder="Lütfen süreyi giriniz.">
      <button @click="startMethod">Başla</button>
      <div class="result">
        <h3>Kalan Süre</h3>
        <p>
          {{timer2}}
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return{
      timer:null,
      timer2:0

    }
  },
  methods:{
    startMethod(){
      this.timer2=this.timer
      let myInterval = setInterval(()=>{
        this.timer2--
        if(this.timer2==0){
          alert("bitti")
          clearInterval(myInterval); 
        }
      },1000)
    }
  }
}
</script>

<style>
  .container{
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
  }
  h1 {
    text-align: center;
    font-weight: 600;
    font-size: 40px;
    margin-bottom: 30px;
  }
  input{
    padding: 5px 15px;
    border: none;
    border-bottom: 1px solid #ccc;
    font-size: 30px;
    width: 300px;
    text-align: center;
    display: block;
    margin: 0 auto 15px;
  }
  button{
    display: block;
    background: #760000;
    border: none;
    color: #fff;
    padding: 12px 30px;
    font-size: 15px;
    border-radius: 7px;
    margin: 0 auto;
    width: 100px;
  }
  .result{
    text-align: center;
    margin: 30px auto;
  }
  .result h3{
    font-size: 40px;
    font-weight: 100;
  }
  .result p{
    font-size: 30px;
    font-weight: 500;
  }
</style>
