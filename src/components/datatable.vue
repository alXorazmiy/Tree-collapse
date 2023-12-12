<template>
    <div class = 'container'>
        <div class="datatable">
            <div class="table">
                <div class="table-header">
                    <div class="table-header_item" v-for="item in headers" :key="item" :style="{width: item.width + 'px'}">{{ item.name }}</div>
                </div>
                <div class="table-body">
                    <div class="table-body_item" v-for="item in data" :key="item">
                        <p class = "name" :style="{width: data_width[0] + 'px'}">{{ item.name }}</p>
                        <p class = "age" :style="{width: data_width[1] + 'px'}">{{ item.age }}</p>
                        <p class = "address" :style="{width: data_width[2] + 'px'}">{{ item.address }}</p>
                        <div class = "tags" :style="{width: data_width[3] + 'px'}">
                            <p><span :class = "item.status == 'loser'? 'danger': 'success'">{{ item.status }}</span></p>
                            <p><span class = 'job' v-show="item.job !=''">{{ item.job }}</span></p>
                        </div>
                        <div class = "action" :style="{width: data_width[4] + 'px'}">
                            <div>Invite- {{ item.name }}</div>
                            <div>Delete</div>
                            <div>More actions <i class="fa-solid fa-chevron-down"></i></div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import {defineProps, onMounted, ref} from 'vue'
const {headers, data} = defineProps(['headers', 'data'])
const data_width = ref([])


onMounted(()=>{
    let list = []
    for (let item in headers) {
        list.push(headers[item].width)
    }
    data_width.value = list
})


</script>

<style>

</style>