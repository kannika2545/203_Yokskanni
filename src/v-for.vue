<!--V-for-->
<script setup>
  const foods = ['steak','salad','tomyum','fried rice']
  const students = [
    {stdId: 1234, stdName: 'Kannika'},
    {stdId: 1234, stdName: 'Siraphob'},
    {stdId: 1234, stdName: 'Jariyawadee'}
  ]
  const course = {
    title : 'INT203 Client II',
    credit: 3,
    class: 'lecture & lab '
  }
  
</script>
 
<template>
  <h1>Food List</h1>
  <ul>
    <li v-for="(food, index) in foods" :key="index">{{food}}</li> <!--ขอให้กำหนด Key ของข้อมูลทุกครั้ง-->
  </ul>

  <ul>
    <li v-for="student in students" :key="student.stdId"> {{ student.stdId }} : {{ student.stdName}}</li>
  </ul>

  <ul>
    <li v-for="(propValue, propKey, index) in course" :key="index"> 
      {{ index }} _ {{propKey}} : {{propValue}}
    </li>
  </ul>
</template>
 
<style>

</style>