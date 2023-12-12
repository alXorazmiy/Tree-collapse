<template>
    <div class = 'container'>
        <Datatable :headers = 'headers' :data = 'data' />
    </div>
</template>

<script setup>
import Datatable from '../components/datatable.vue'

const headers = [
    {name : 'Name', width: 100},
    {name : 'Age', width: 50},
    {name : 'Address', width: 250},
    {name : 'Tags', width: 200},
    {name : 'Action', width: 400},
]

const data = [
    {
        id : 1,
        name : "John Brown",
        age : 32,
        address : 'New York No 1 Lake Park',
        status : 'nice',
        job : 'developer',
    },
    {
        id : 2,
        name : "Jim Green",
        age : 42,
        address : 'New York No 1 Lake Park',
        status : 'loser',
        job : '',
    },
    {
        id : 1,
        name : "Joe Black",
        age : 32,
        address : 'New York No 1 Lake Park',
        status : 'cool',
        job : 'teacher',
    },
]






</script>
