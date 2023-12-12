
<template>
    <div class="container">
        <div class="box">
            <div class="tree-collapse">
                <Tree :data = "tree_list" />           
            </div>
        </div>
    </div>
</template>

<script setup>
import Tree from '../components/tree.vue'
const tree_list = [
    {
        parent : "Models",
        child: [
            {
                parent : "Data warehouse",
                child: ['Report samples', 'Sales performance']
            }
        ]   
    },

    {
        parent : "Statistics",  
    },

]

</script>
