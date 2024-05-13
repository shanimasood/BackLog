<template>
    <div class="card">
      <DataTable :showGridlines="true" :stripedRows="true" :value="backLogData" rowGroupMode="subheader" groupRowsBy="groupHeader.name" sortMode="single"
        sortField="groupHeader.name" :sortOrder="1" scrollable scrollHeight="400px" tableStyle="min-width: 100%">
        <template #empty>
          <p style="margin:0%;padding:0%;text-align: center;">No BackLog Found.</p>
        </template>
        <Column field="groupHeader.name" header="Group Header"></Column>
        <Column v-for="(column, index) in tableColumn" :key="index" :field="column.prop" :header="column.headerLabel"
          :filterField="column.prop" :style="{ minWidth: column.columnsWidth + 'rem !important' }"></Column>
        <template #groupheader="slotProps">
          <div class="flex align-items-center gap-2">
            <span>{{ slotProps.data.groupHeader.name }}</span>
          </div>
        </template>
        <!-- <template #groupfooter="slotProps">
                  <div class="flex justify-content-end font-bold w-full">Total Task: {{ calculateCustomerTotal(slotProps.data.representative.name) }}</div>
              </template> -->
      </DataTable>
    </div>
  </template>
  <script setup>
  import { ref } from "vue";
  const backLogData = ref([
    {
      id:1,
      groupHeader:{
        name:"User Story 1"
      },
      backLogTask:'task1',
      assignedTo:'',
      status:'',
      originalEstmt:'',
      day1:'',
      day2:'',
      day3:'',
      day4:'',
      day5:'',
      sprintReview:''
    },
    {
      id:2,
      groupHeader:{
        name:"User Story 1"
      },
      backLogTask:'task2',
      assignedTo:'',
      status:'',
      originalEstmt:'',
      day1:'',
      day2:'',
      day3:'',
      day4:'',
      day5:'',
      sprintReview:''
    },
    {
      id:3,
      groupHeader:{
        name:"User Story 2"
      },
      backLogTask:'task1',
      assignedTo:'',
      status:'',
      originalEstmt:'',
      day1:'',
      day2:'',
      day3:'',
      day4:'',
      day5:'',
      sprintReview:''
    },
    {
      id:4,
      groupHeader:{
        name:"User Story 2"
      },
      backLogTask:'task2',
      assignedTo:'',
      status:'',
      originalEstmt:'',
      day1:'',
      day2:'',
      day3:'',
      day4:'',
      day5:'',
      sprintReview:''
    }
  ])
  const tableColumn = ref([
    {
      prop: "backLogTask",
      headerLabel: "BACKLOG TASK & ID",
      columnsWidth: '15'
    },
    {
      prop: "assignedTo",
      headerLabel: "ASSIGNED TO",
      columnsWidth: '10'
    },
    {
      prop: "status",
      headerLabel: "STATUS",
      columnsWidth: '10'
    },
    {
      prop: "originalEstmt",
      headerLabel: "ORIGINAL ESTIMATE",
      columnsWidth: '15'
    },
    {
      prop: "day1",
      headerLabel: "DAY 1",
      columnsWidth: '5'
    },
    {
      prop: "day2",
      headerLabel: "DAY 2",
      columnsWidth: '5'
    },
    {
      prop: "day3",
      headerLabel: "DAY 3",
      columnsWidth: '5'
    },
    {
      prop: "day4",
      headerLabel: "DAY 4",
      columnsWidth: '5'
    },
    {
      prop: "day5",
      headerLabel: "DAY 5",
      columnsWidth: '5'
    },
    {
      prop: "sprintReview",
      headerLabel: "SPRINT REVIEW",
      columnsWidth: '10'
    },
  ])
  </script>