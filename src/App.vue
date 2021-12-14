<template>
  <div class="flex flex-col">
    <h1>CONNECTION APP</h1>
    <div class="flex flex-row justify-between">
      <app-table class="mr-20"></app-table>

      <app-cable class="mx-20"></app-cable>

      <app-switches class="mx-20"></app-switches>

      <app-ip class="mx-20"></app-ip>

      <app-computer class="mx-20"></app-computer>
    </div>
    <div class="flex justify-end">
      <button class="border-2 p-4">Import Data</button>
      <button class="border-2 p-4">Download Data</button>
    </div>
  </div>
</template>
<script>
import draggable from "vuedraggable";

import AppTable from "./components/AppTable.vue";
import AppCable from "./components/AppCable.vue";
import AppSwitches from "./components/AppSwitches.vue";
import AppIp from "./components/AppIp.vue";
import AppComputer from "./components/AppComputer.vue";

export default {
  name: "App",
  components: {
    AppTable,
    AppCable,
    AppSwitches,
    AppIp,
    AppComputer,
    draggable,
  },
  data() {
    return {};
  },
};
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
