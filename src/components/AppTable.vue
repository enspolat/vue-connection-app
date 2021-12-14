<template>
  <div>
    <div v-if="show" class="flex justify-center m-4">
      <div>
        <h3 class="text-xl text-yellow-500">Add Tables</h3>
        <input v-model="table" type="text" class="border-2 m-2" />
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
          close
        </button>
      </div>
    </div>
    <div class="m-4 justify-between">
      Tables
      <button class="rounded-full border-2 w-12 h-12" @click="tablesAdd()">
        +
      </button>
    </div>
    <div class="border-2">
      <div
        class="flex flex-col text-center p-2 break-words"
        v-for="table in tables"
        :key="table.id"
      >
        <div
          class="border-2 flex justify-between text-xl pl-2 items-center h-12 w-64 break-words"
        >
          <div
            class="border-2 flex justify-between text-xl pl-2 items-center h-12 w-64 break-words"
            v-on:dragstart="dragStart"
            v-on:drag="dragging"
            draggable="true"
            id="dragtarget"
          >
            <p class="break-worlds">{{ table.text }}</p>

            <button
              class="bg-red-300 hover:bg-red-600 hover:shadow-xl h-12 w-12 text-3xl text-white"
              @click="remove(table.id)"
            >
              X
            </button>
          </div>
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
      table: "",
      item: {
        id: "",
        text: "",
      },

      tables: [{ id: 1, text: "play" }],
    };
  },
  methods: {
    add() {
      if (this.table.length === 0) {
        return;
      }
      this.tables.push({
        id: Math.random(),
        text: this.table,
      });
      this.table = "";
    },
    tablesAdd() {
      this.show = true;
    },
    close() {
      this.show = false;
    },
    remove(tableId) {
      this.tables = this.tables.filter((table) => table.id !== tableId);
    },
  },
};
</script>

<style></style>
