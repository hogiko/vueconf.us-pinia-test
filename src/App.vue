<template>
  <div class="container">
    <Card>
      <h4>Add new item</h4>
      <AddItem />
    </Card>
    <Card>
      <h4>Your items ({{ cart.itemsCount }})</h4>
      <ItemsList />
    </Card>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Card from "@/components/Card.vue";
import AddItem from "@/components/AddItem.vue";
import ItemsList from "@/components/ItemsList.vue";
import { useCartStore } from "@/store/cart";


export default defineComponent({
  components: { Card, AddItem, ItemsList },
  setup() {
    const cart = useCartStore();
    return { cart }    
  }
})
</script>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
