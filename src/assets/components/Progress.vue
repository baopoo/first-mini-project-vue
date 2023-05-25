<template>
    <div class="row mt-3">
        <h2 class="text-primary">Information Quantity</h2>
        <div class="progress col-12">
            <div class="progress-bar" role="progressbar" 
                :style="{width: value + '%'}" aria-valuemin="0" aria-valuemax="100">
                {{ value }}%</div>
        </div>
    </div>
</template>
<script>
export default {
    props: {
        value: {
            type: Number,
            require: true,
            default: 0
        }
    }
}
</script>
<style scoped>
.row >* {
    padding: 0;
}
</style>