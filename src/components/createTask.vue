<template>
    <el-row :gutter="20">
        <el-col :md="2" :lg="2"></el-col>
        <el-col :md="6" :lg="6">
            <label for="userStory">User Story Name
                <InputText style="width: 100%;" size="small" id="userStory" v-model="userStory" aria-describedby="userStory-help" />
            </label>
        </el-col>
        <el-col :md="16" :lg="16"></el-col>
    </el-row>
    <el-row :gutter="20">
        <el-col :md="2" :lg="2"></el-col>
        <el-col :md="6" :lg="6">
            <label for="taskName">Task Name
                <InputText style="width: 100%;" size="small" id="taskName" v-model="taskName" aria-describedby="taskName-help" />
            </label>
        </el-col>
        <el-col :md="6" :lg="6">
            <label for="assignTo">Assign To
                <InputText style="width: 100%;" size="small" id="assignTo" v-model="assignTo" aria-describedby="assignTo-help" />
            </label>
        </el-col>
    </el-row>
</template>

<script setup>
import { ref } from 'vue';

const userStory = ref(null);
const taskName= ref(null);
const assignTo =ref(null)
</script>
