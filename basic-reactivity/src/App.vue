<script setup>
import { ref, computed } from 'vue'
console.clear()
const myNotes = ref([])
const newNote = ref('')
const keywords = ref('')
const addNote = () => myNotes.value.push(newNote.value)
const filterSearch = computed( () => 
  myNotes.value.filter((myNote) =>
    myNote.toLowerCase().includes(keywords.value.toLowerCase())
  )
)
</script>

<template>
<!-- empty array are true , not empty array are still true-->
<div v-show="myNotes != ''"> 
  Filter Note: <input type="text" v-model="keywords" >
  <ul>
    <li v-for="(myNote, index) in filterSearch" :key="index">
     {{myNote}}    
    </li>
  </ul>
</div>

  New Note: <input type="text" v-model="newNote" />
  <button @click="addNote" style="cursor:pointer">Add Note</button>
</template>

<style></style>