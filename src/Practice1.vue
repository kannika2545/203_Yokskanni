<!--Practices1 in App.vue-->
<script setup>
  const myAccount = [
    {name: 'salary', amount: 10000},
    {name: 'rent', amount: -2500},
    {name: 'parking fee', amount: 0},
    {name: 'car fuel', amount: -600},
    {name: 'commission', amount: 5500}
  ]
</script>
 
<template>

  <div>
    <h1 class="flex justify-center uppercase p-5 text-2xl font-bold tracking-widest ">My Account</h1>
  </div>

  <div class=" mx-2 grid grid-cols-1 gap-4 md:hidden">
    <ul v-for="(account, index) in myAccount" :key="index">
      <li class=" py-2 border-2 border-gray-200 pl-6 rounded-lg" v-if="account.amount != 0">
        <b class="pr-10">Name:</b>{{account.name}} <br>
        <b class="pr-6">Amount:</b>     
        <span class="rounded-lg" :style="account.amount > 0 ? 'background-color: rgb(217 249 157)' : 'background-color: rgb(254 202 202)'">
        {{account.amount}}
        </span>
      </li>
    </ul>
    
    <p class= "p-4 flex justify-end">
      <b class="pr-3">Net Total:</b> {{ myAccount.reduce((total, account) => total + account.amount, 0) }}
    </p>

  </div>

  <div class=" hidden md:block">
    <table class="mx- relative w-full text-xl xl:text-3xl">
      <thead class="border-2 border-gray-200 bg-gray-100">
        <tr>
          <th class="">Name</th>
          <th>Amount</th>
        </tr>
      </thead>
      <tbody v-for="(account, index) in myAccount" :key="index">
        <tr v-if="account.amount != 0">
          <td class="text-center">{{account.name}}</td>
          <td class="text-center">
            <span class="rounded-lg" :style="account.amount > 0 ? 'background-color: rgb(217 249 157)' : 'background-color: rgb(254 202 202)'">
            {{account.amount}}
            </span>
          </td>
        </tr>       
      </tbody>
    </table>
    
    <p class="text-center font-semibold p-8 text-xl xl:text-3xl">
      <!-- reduce is higher order function -->
      <!-- (total, account) => total + account.amount (arrow function syntax) -->
      <b class="pr-7">Net Total:</b> {{ myAccount.reduce((total, account) => total + account.amount, 0) }}
    </p>
 <!-- 
   #round 1 (0,account#1) : 0+10000
   #round 2 (10000,account#2) : 10000+(-2500)
   #round 3 (7500,account#3) ...   
 -->
  </div>

</template> 

<style>

</style>