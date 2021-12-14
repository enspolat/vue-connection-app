<template>
  <div>
    <div v-if="show" class="flex justify-center m-4">
      <div>
        <h3 class="text-xl text-yellow-500">Add IPs</h3>
        <input v-model="IP" type="text" class="border-2 m-2" />
      </div>
      <div>
        <button
          class="bg-blue-300 hover:bg-blue-600 hover:shadow-xl flex flex-row text-center p-2 m-2"
          @click="add()"
        >
          add
        </button>
        <button
          class="bg-red-300 hover:bg-red-600 hover:shadow-xl flex flex-row text-center p-2 m-2"
          @click="close()"
        >
          kapat
        </button>
      </div>
    </div>
    <div class="m-4 justify-between">
      IPs
      <button class="rounded-full border-2 w-12 h-12" @click="IPsAdd()">
        +
      </button>
    </div>
    <div class="border-2">
      <div
        class="flex flex-col text-center p-2 break-words"
        v-for="IP in IPs"
        :key="IP.id"
      >
        <div
          class="border-2 flex justify-between text-xl pl-2 items-center h-12 w-64 break-words"
        >
          <p class="break-worlds">{{ IP.text }}</p>
          <button
            class="bg-red-300 hover:bg-red-600 hover:shadow-xl h-12 w-12 text-3xl text-white"
            @click="remove(IP.id)"
          >
            X
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      show: false,
      IP: "",
      item: {
        id: "",
        text: "",
      },
      IPs: [{ id: 1, text: "play" }],
    };
  },
  methods: {
    add() {
      if (this.IP.length === 0) {
        return;
      }
      this.IPs.push({
        id: Math.random(),
        text: this.IP,
      });
      this.IP = "";
    },
    IPsAdd() {
      this.show = true;
    },
    close() {
      this.show = false;
    },
    remove(IPId) {
      this.IPs = this.IPs.filter((IP) => IP.id !== IPId);
    },
  },
};
</script>

<style></style>
