<!--ทำให้ตัวแปร Sync กับ template อยู่เสมอ-->

<script setup>
  import {ref} from 'vue' 
  //ทำ ref ฟังก์ชันเพื่อให้ตัวแปรนั้นเป็น reactive variable ก็คือตรงนี้มีการเปลี่ยนแปลงค่า ตรงนู้นก็จะรับรู้การเปลี่ยนแปลงนั้นด้วย 
  console.clear()
  //เมื่อไหร่มีการใช้ ref function แล้วต้องการให้แสดงค่า ต้องห้อยท้ายด้วย .value ถ้าไม่ใส่จะไม่ทำงาน
  const counter = ref(1) //ค่าเริ่มต้นของตัวแปร คืนค่าเป็น object ดังนั้นต้องมี value
  const isEmpty = ref(false)
  const msg = ref('Hello, String ref')
  const items = ref(['pen','book','mouse'])
  const product = ref({
    productId: 1,
    productName: 'Notebook'
  })
  console.log(items.value[0])
  console.log(product.value)
  console.log(product.value.productName)

  //setTimeout(() => console.log(++counter), 3000)
  //setInterval(() => console.log(++counter.value), 1000)
</script>
 
<template>
  <p>Counter: {{counter}}</p>
  <p>Empty: {{isEmpty}}</p>
  <p>Items: {{items}}</p>
  <p>Items[1]: {{items[1]}}</p>
  <p>Product: {{product.productName}}</p>
</template>
 
<style>

</style>