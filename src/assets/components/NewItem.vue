<template>
    <div class="row">
        <div class="form-group col-12">
            <label for="item">Add your information: </label>
            <textarea class="form-control mt-2" id="item" rows="3" v-model="item"></textarea>
        </div>
        <button 
            type="button" 
            class="btn btn-primary col-3 mt-2 mx-auto" 
            @click="onClickCreateItem()"
        >Add info</button>
    </div>
</template>
<script>
export default {
    data() {
        return {
            item: ''
        }
    },    
    methods: {
        onClickCreateItem(){
            if (this.item === '') {
                this.item = 'Bảo đẹp trai !'
            }
            this.$emit('addItem', this.item);
            this.item = ''
        }
    }
}
</script>
<style>

</style>