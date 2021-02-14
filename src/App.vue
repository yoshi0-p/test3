<template>
  <div id="app">
    <input type="text" v-model="getText">
    <button @click="showAdress()" type="submit">変換 </button>
     <p>住所：{{pick}}</p>
  </div>
</template>

<script>
import axios from "axios";
export default {
  
  data(){
    return{
      show:"", 
      getText:""
    };
  },
   methods:{
     async showAdress(){
      let item = await axios.get(`https://apis.postcode-jp.com/api/v3/postcodes/${this.getText}?&apikey=fabCn3nwAAosqqjhmKDAC5fhlZKgNh6fPvWwBZY`);
      /*const picks = item.data; 
      this.show = picks.allAddress; */
      this.show =item.data.allAddress;
    }
  }
};
</script>