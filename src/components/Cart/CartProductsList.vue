<template>
  <div class="d-flex flex-column flex-wrap p-1">
    <h5 class="border-bottom pb-3">Mon panier</h5>
    <cart-product-item v-for="item in cart" :key="item.id" :item="item"></cart-product-item>
    <template v-if="cart.length">
      <hr class="w-100"/>
      <span>Total : {{ total }} €</span>
    </template>
  </div>
</template>

<script>
import CartProductItem from './CartProductItem.vue';
export default {
components: {
  CartProductItem,
},
props: ['cart'],
computed: {
  total() {
    return this.cart.reduce((acc, value) => {
      acc += value.price;
      return acc;
    }, 0)
  }
}
};
</script>
<style>
</style>