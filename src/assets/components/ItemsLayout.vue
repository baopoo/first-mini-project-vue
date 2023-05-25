<template>
    <div class="row g-2">
        <app-items v-for="(item, index) in items" :index="index" :key="index" :item="item">
        </app-items>
    </div>
</template>
<script>
import Items from './Items.vue';

export default {
    components: {
        'app-items': Items
    },
    props: {
        items: {
            type: Array,
            required: true,
        }
    },
}
</script>
<style>
div {
    width: 100%;
}
    
</style>