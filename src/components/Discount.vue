<template>
  <div class="discount">
    <h4>지금 결제하면 {{this.discount}}% 할인</h4>
  </div>
</template>

<script>
export default {
name:"Discount",
data(){
  return{
  discount:30,
  }
},
mounted(){
  setInterval(()=>{
    this.discount--;
  },1000)
}

};

</script>

<style>

</style>