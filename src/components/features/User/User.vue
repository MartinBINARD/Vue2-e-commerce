<template>
        <div class="d-flex flex-row">
          <transition name="left" appear>
            <shop class="w-75"></shop>
          </transition>
          <transition name="right" appear>
            <cart class="w-25"></cart>
          </transition>
        </div>
       </template>
<script>
import Shop from './Shop/Shop.vue';
import Cart from './Cart/Cart.vue';

export default {
        components: {
                Shop,
                Cart
        }
}
</script>

<style scoped>
 @keyframes fromleft {
   from {
     transform: translateX(-20px);
   }
   to {}
 }
 @keyframes fromright {
   from {
     transform: translateX(20px);
   }
   to {}
 }
 .left-enter-active {
   animation: fromleft 1s;
 }
 .right-enter-active {
   animation: fromright 1s;
 }
</style>