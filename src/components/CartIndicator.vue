<template>
  <router-link class="header__cart" aria-label="Корзина с товарами" :to="{ name: 'cart' }">
    <span v-if="cartLoading === true">Загрузка корзины...</span>
    <div v-if="cartLoading === false">
      <svg width="30" height="21" fill="currentColor">
        <use xlink:href="#icon-cart"></use>
      </svg>
      <span class="header__count" aria-label="Количество товаров">
        {{ $store.state.cartProducts.length }}
      </span>
    </div>
  </router-link>
</template>

<script>
export default {
  data() {
    return {
      cartLoading: false,
    };
  },
  props: ['cartLoading'],
};
</script>
