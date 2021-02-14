<template >
  <div id="header">
    
  
   
  </div>
</template>

<script>

export default {
  data(){
    return{
      show:"",
      
    };
  },
  props:["parentText"],
  method:{
     async showAdress(){
      let item = await axios.get('https://apis.postcode-jp.com/api/v4/postcodes/${parenttText}?allAdress');
     this.show = item.data;
    }
  }
}
</script>

<style scoped>
.button{
  height:300px;
}
</style>