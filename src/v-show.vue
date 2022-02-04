<!--V-show-->
<script setup>
  const count = 0 //false ตาม implicit type conversions
  const username = '' //false
</script>
 
<template>
<!--เมื่อไหร่ที่ v-show เป็น false มันจะเอา display ="none" ใส่ให้ทันที-->
<!--ถ้าเป็น true มันจะแสดง ถ้า false มันจะซ่อน-->
  <p v-show = "count!==0"> Counter: {{count}}</p> <!--false-->
  <h1 v-show = "count==0"> Counter: {{count}}</h1> <!--true-->

  <h3 v-show ="count"> Counter: {{count}} </h3>  <!--false-->
  <p v-show ="!count"> Counter: {{count}} </p> <!--true-->

  <p>UserName: {{username}}</p>
  <p v-show="!username" style="color: brown;">Please enter your username!</p>
</template>

 
<style>

</style>
