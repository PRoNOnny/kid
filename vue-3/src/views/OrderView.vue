<script setup>
import { ref } from 'vue'
const od = sessionStorage.getItem('prod')? JSON.parse(sessionStorage.getItem('prod')) : []
const items =  ref(od)

const calculate = () => {
  let price = 0
  od.map(element => {
    price = price +(element.price * element.qty)
    return
  });
  return price
}

</script>

<template>
<h1>FASHION STORE <span style="color:darkgoldenrod; margin-reight: 5px">  ORDER</span></h1> 

<BTableSimple style="margin: 1rem 2rem 2rem" hover small caption-top responsive>

  <BThead head-variant="dark">
    <BTr>
      <BTh colspan="1">No.</BTh>
      <BTh colspan="5">รายการสินค้า</BTh>
      <BTh colspan="2">ราคาต่อชิ้น</BTh>
      <BTh colspan="2">จำนวน</BTh>
      <BTh colspan="2">ราคารวม</BTh>
    </BTr>
  </BThead>
  <BTbody>
    <BTr v-for="(item , index) in items" :key="item.id" :index="index">
      <BTh colspan="1">{{ index + 1 }}</BTh>
      <BTh colspan="5">{{ item.name }}</BTh>
      <BTh colspan="2">{{ item.price}}</BTh>
      <BTh colspan="2">{{ item.qty }}</BTh>
      <BTh colspan="2">{{ item.price * item.qty }}</BTh>
    </BTr>

  </BTbody>
  <BTfoot>
    <BTr>
      <BTd colspan="11" variant="secondary" class="text-end"> Total: <b>{{ calculate() }} </b> bath</BTd>
    </BTr>
  </BTfoot>
</BTableSimple>
<BButton pill style="width:25%!important">Pay Online</BButton>
</template>

<style>
h1{
  font-weight: bold;
}

th {
  height: 33px;
}
</style>