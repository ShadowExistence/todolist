<script setup lang="ts">
  import {ref, computed} from 'vue'


  var list = ref([])
  var string = ref()
  function add(){
    list.value.push(string.value)
    console.log(`added ${string.value}`)
  }

  function del(i){
    list.value.splice(i,1);
  }

  

</script>


<template >
 <ul>
  <li  v-for="(q,i) in list" :key="i" @click="del(i)">{{q}}</li>
 </ul>
 <input @keydown.enter="add" v-model="string" type="text" />
 <button  @click="add">Add</button>
</template>

