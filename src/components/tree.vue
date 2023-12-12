<template>
    <div class = 'tree'>
        <div class = 'tree-items'>
            <div  v-for="item in data" :key="item">
                <div class = 'tree-items_item' >
                    <p class = "item-hover"></p> <p class = "tree-items_item-name" @click="show_child(item.parent)"><i class="fa-solid fa-caret-right" :class="showChild == item.parent? 'active': ''"></i> {{ item.parent }}</p>
                </div>
                <div  v-for="child in item.child" :key="child" >
                    <div class = 'tree-items_item child' :class="showChild == item.parent? 'active': ''">
                        <p class = "item-hover"></p> <p class = "tree-items_item-name tree-child_item" @click="show_child_item(child.parent)"><i class="fa-solid fa-caret-right" :class="showChildItem == child.parent ? 'active': ''"></i> {{ child.parent }}</p>
                    </div>
                    <div  v-for="child2 in child.child" :key="child2" @click="not_working">
                        <div class = 'tree-items_item child2' :class="showChildItem == child.parent ? 'active': ''">
                            <p class = "item-hover"></p> <p class = "tree-items_item-name tree-child_item" > {{ child2 }}</p>
                        </div>
                        
                    </div>
                </div>
            </div>
        </div>
    </div>
    
</template>

<script setup>
import {defineProps, ref} from 'vue'
const {data} = defineProps(['data',])
const showChild = ref(null)
const showChildItem = ref(null)

function show_child(parent){
    showChildItem.value = null
    if (showChild.value == parent){
        showChild.value = null
    }
    else{
        showChild.value = parent
    }
}

function show_child_item(child){
    if (showChildItem.value){
        showChildItem.value = null
    }
    else{
        showChildItem.value = child
    }
}

function not_working(){

}

</script>

<style>

</style>