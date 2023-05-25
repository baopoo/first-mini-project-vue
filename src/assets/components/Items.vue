<template>
    <div class="col-sm-6 col-md-4 col-lg-3">
        <div class="card">
            <div class="card-body d-flex justify-content-between align-items-center">
                <span> {{ item }} </span>
                <button slot="deleteItem" class="btn btn-danger ms-1" @click="onClickDeleteItem(index)">Delete</button>
            </div>
        </div>
    </div>
</template>
<script>
import { evenBus } from '../../main';


export default {
    props: {
        item: {
            type: String,
            required: true  
        },
        index: {
            type: Number,
            required: true
        }
    },
    methods: {
        onClickDeleteItem(index) {
            evenBus.$emit('deleteItem', index);
        }
    }
    
}
</script>
<style>
    
</style>