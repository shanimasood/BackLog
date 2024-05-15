<template>
    <el-row :gutter="20">
        <el-col :md="2" :lg="2"></el-col>
        <el-col :md="6" :lg="6">
            <label for="userStory">User Story Name
                <InputText style="width: 100%;" size="small" id="userStory" v-model="userStory"
                    aria-describedby="userStory-help" />
            </label>
        </el-col>
        <el-col :md="16" :lg="16"></el-col>
    </el-row>
    <el-row :gutter="20">
        <el-col :md="2" :lg="2"></el-col>
        <el-col :md="6" :lg="6">
            <label for="taskName">Task Name
                <InputText style="width: 100%;" size="small" id="taskName" v-model="taskName"
                    aria-describedby="taskName-help" />
            </label>
        </el-col>
        <el-col :md="6" :lg="6">
            <label for="assignTo">Assign To
                <InputText style="width: 100%;" size="small" id="assignTo" v-model="assignTo"
                    aria-describedby="assignTo-help" />
            </label>
        </el-col>
    </el-row>
    <el-row :gutter="20">
        <el-col :md="2" :lg="2"></el-col>
        <el-col :md="6" :lg="6">
            <label for="status">Status
                <InputText style="width: 100%;" size="small" id="status" v-model="status"
                    aria-describedby="status-help" />
            </label>
        </el-col>
        <el-col :md="6" :lg="6">
            <label for="originalEstmt">Original Estimate
                <InputText style="width: 100%;" size="small" id="originalEstmt" v-model="originalEstmt"
                    aria-describedby="originalEstmt-help" />
            </label>
        </el-col>
    </el-row>
    <el-row :gutter="20">
        <el-col :md="2" :lg="2"></el-col>
        <el-col :md="6" :lg="6">
            <label for="day1">Day 1
                <InputText style="width: 100%;" size="small" id="day1" v-model="day1" aria-describedby="day1-help" />
            </label>
        </el-col>
        <el-col :md="6" :lg="6">
            <label for="day2">Day 2
                <InputText style="width: 100%;" size="small" id="day2" v-model="day2" aria-describedby="day2-help" />
            </label>
        </el-col>
        <el-col :md="6" :lg="6">
            <label for="day3">Day 3
                <InputText style="width: 100%;" size="small" id="day3" v-model="day3" aria-describedby="day3-help" />
            </label>
        </el-col>
    </el-row>
    <el-row :gutter="20">
        <el-col :md="2" :lg="2"></el-col>
        <el-col :md="6" :lg="6">
            <label for="day4">Day 4
                <InputText style="width: 100%;" size="small" id="day4" v-model="day4" aria-describedby="day4-help" />
            </label>
        </el-col>
        <el-col :md="6" :lg="6">
            <label for="day5">Day 5
                <InputText style="width: 100%;" size="small" id="day5" v-model="day5" aria-describedby="day5-help" />
            </label>
        </el-col>
    </el-row>
    <el-row :gutter="20">
        <el-col :md="2" :lg="2"></el-col>
        <el-col :md="12" :lg="12">
            <label for="sprintReview">Sprint Review
                <InputText style="width: 100%;" size="small" id="sprintReview" v-model="sprintReview"
                    aria-describedby="sprintReview-help" />
            </label>
        </el-col>
    </el-row>
    <br>
    <el-row>
        <el-col :md="2" :lg="2"></el-col>
        <el-col :md="3" :lg="3">
            <el-button :disabled="formDisabled" @click="addBackLog" style="width: 100%; height: 100%;" type="success">Add</el-button>
        </el-col>
    </el-row>
</template>

<script setup>
import { computed, ref } from 'vue';

const userStory = ref(null);
const taskName = ref(null);
const assignTo = ref(null)
const status = ref(null)
const originalEstmt = ref(null)
const day1 = ref(null)
const day2 = ref(null)
const day3 = ref(null)
const day4 = ref(null)
const day5 = ref(null)
const sprintReview = ref(null)
function resetForm(){
    userStory.value=null
    taskName.value=null 
    assignTo.value=null 
    status.value=null 
    originalEstmt.value=null 
    day1.value=null 
    sprintReview.value=null
}
function addBackLog(){
    resetForm()
}
const formDisabled = computed(() => {
    let isDisable = [userStory.value, taskName.value, assignTo.value, status.value, originalEstmt.value, day1.value, sprintReview.value].every((field) => field != undefined && field != null && field != "");
    return !isDisable;
})
</script>
