<template>
  <div class="container d-flex flex-column gap-3">
    <app-progress :value="quantity"></app-progress>
    <app-newItem @addItem=" addItem($event)"></app-newItem>
    <app-itemsLayout :items="items"></app-itemsLayout>
  </div>
</template>

<script>
import ItemsLayout from './assets/components/ItemsLayout.vue';
import NewItem from './assets/components/NewItem.vue';
import Progress from './assets/components/Progress.vue';
import { evenBus } from './main';
import Swal from 'sweetalert2'

export default {
  components: {
    'app-itemsLayout': ItemsLayout,
    'app-newItem': NewItem,
    'app-progress': Progress,
  },
  data () {
    return {
      items: [],
      maxItems: 4,
      quantity: 0
    }
  },
  methods: {
    addItem(item){
      if (this.quantity < 100) {
        this.quantity = ((this.items.length + 1) / this.maxItems) * 100;
        this.items.push(item);
      } else {
        Swal.fire('OOPS !','The information quantity is full, please delete anything to add new information !','warning')
      }
    },
  },

  created(){
    evenBus.$on('deleteItem', (index) => {
      this.items.splice(index, 1);
      this.quantity = (this.items.length / this.maxItems) * 100;
      console.log(this.quantity);
    })
  }
}
</script>

<style>

</style>
