<script setup>
import { ref, computed } from 'vue'
console.clear()
const myNotes = ref([])
const newNote = ref('')
const addNote = () => myNotes.value.push(newNote.value)

//const filterSearch = computed ( () => {
//  const text = newNote.value.trim()
//    return myNotes.value.filter(item => {
//      return item.newNote.indexOf(text) > -1
//    }) 
//})

</script>

<template>

<div v-show="myNotes != ''">
  Filter Note: <input type="text" v-model="filterSearch" >

<!--
 <ul>
   <li v-for="(search, index) in filterSearch" :key="index">
     {{search.newNote}}
    </li>
  </ul>
--> 

  <ul>
    <li v-for="(myNote, index) in myNotes" :key="index">
     {{myNote}}
    </li>
  </ul>
</div>

  New Note: <input type="text" v-model="newNote" />
  <button @click="addNote" style="cursor:pointer">Add Note</button>
</template>

<style></style>