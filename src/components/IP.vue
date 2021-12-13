<template>
        <div>
          <div v-if="show" class="flex justify-center m-4">
      <div>
        <h3 class="text-xl text-yellow-500">Add IPs</h3>
        <input v-model="IP" type="text" class="border-2 m-2">
      </div>
      <div>
       <button class="bg-blue-300 hover:bg-blue-600 hover:shadow-xl flex flex-row text-center  p-2 m-2" @click="add()">  add  </button>
      <button class="bg-red-300 hover:bg-red-600 hover:shadow-xl flex flex-row text-center  p-2 m-2" @click="close()">kapat</button>
      </div>

      </div> 
       <div class="m-4 justify-between">IPs <button class="rounded-full border-2 w-12 h-12" @click="IPsAdd()">+</button></div>
      <div class="flex flex-col text-center" v-for="IP in IPs" :key="IP.id">
        <div class="border-2 p-4 " >{{IP.text}}</div>
      </div>
      </div>
</template>

<script>
export default {

data() {
    return{
      show: false,
      IP: "",
      item: {
        id: '',
        text: ''
      },

      IPs: [
        {id: 1, text:'play'}
      ],
    }
  },
  methods: {
    add(){
    if (this.IP.length === 0) {
        return;
      }
      this.IPs.push({
        id: Math.random(),
        text: this.IP,
      });
      this.IP = "";
    },
    IPsAdd(){
      this.show = true
    },
    close(){
    this.show = false
    }
  },
}
</script>

<style>

</style>