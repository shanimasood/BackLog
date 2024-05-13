<template>
  <el-container style="height: 100vh">
    <SideBar @selectedModule="selectedModule"></SideBar>
    <el-container>
      <el-header>
        <h3 style="text-align: center;">AGILE SPRINT BACKLOG TEMPLATE WITH BURNDOWN CHART</h3>
      </el-header>
      <el-main style="padding: 0.1%;">
        <Table v-if="table"></Table>
        <Task v-if="task"></Task>
      </el-main>
    </el-container>
  </el-container>
</template>
<script setup>
import Table from './components/table.vue'
import SideBar from './components/sidebar.vue'
import Task from './components/createTask.vue'
import { ref } from 'vue'
let table = ref(true)
let task = ref(false)
function selectedModule(name) {
  console.log(name)
  if (name == "DashBoard") {
    table.value = true
    task.value = false
  } else if (name == "Create Task") {
    table.value = false
    task.value = true
  }
}
</script>