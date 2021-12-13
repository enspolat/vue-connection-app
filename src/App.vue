<template>
 <div class="flex justify-center"><h1>CONNECTION APP</h1> 
     <Table></Table>

      <Cable></Cable>

      <Switches></Switches>

      <IP></IP>

      <Computer></Computer>   </div>
    <!-- <div class="break-words container flex flex-row justify-between">
      <div>
          <div v-if="show" class="flex justify-center m-4">
      <div>
        <h3 class="text-xl text-yellow-500">Add Tables</h3>
        <input v-model="table" type="text" class="border-2 m-2">
      </div>
      <div>
       <button class="bg-blue-300 hover:bg-blue-600 hover:shadow-xl flex flex-row text-center  p-2 m-2" @click="add()">  add  </button>
      <button class="bg-red-300 hover:bg-red-600 hover:shadow-xl flex flex-row text-center  p-2 m-2" @click="close()">kapat</button>
      </div>

      </div> 
       <div class="m-4 justify-between">Tables <button class="rounded-full border-2 w-12 h-12" @click="tablesAdd()">+</button></div>
      <div class="flex flex-col text-center" v-for="table in tables" :key="table.id">
        <div class="border-2 p-4 " >{{table.text}}</div>
      </div>
      </div> -->
      
  

      <!-- <div class="flex flex-col text-center">
        <div class="m-4 ">Switches <button class="rounded-full border-2 w-12 h-12"  @click="switchesAdd()">+</button></div>
        <div class="border-2 p-4 " >{{switche.text}}</div>
      </div>

      <div class="flex flex-col text-center">
        <div class="m-4 ">IP <button class="rounded-full border-2 w-12 h-12"  @click="IPAdd()">+</button></div>
        <div class="border-2 p-4 " >{{ip.text}}</div>
      </div>

      <div class="flex flex-col text-center">
        <div class="m-4 ">Computer <button class="rounded-full border-2 w-12 h-12"  @click="computerAdd()">+</button></div>
        <div class="border-2 p-4" >{{computer.text}}</div>
      </div>
    </div> -->
       <div class="flex justify-end ">
      <button class="border-2 p-4">Import Data</button>
      <button class="border-2 p-4">Download Data</button>
    </div>
</template>
<script>

import Table from './components/Table.vue';

import Cable from './components/Cable.vue';

import Switches from './components/Switches.vue';

import IP from './components/IP.vue';

import Computer from './components/Computer.vue'

export default {
 
  name: 'App',
  components: {
    Table,
    Cable,
    Switches,
    IP,
    Computer
  },
  data() {
    return{

    }
  },

  }

</script>



<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
