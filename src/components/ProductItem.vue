<template>
  <div>
    <a class="catalog__pic" href="#" @click.prevent="goToPage('product', { id: product.id })">
      <img :src=product.image :alt=title>
    </a>

    <h3 class="catalog__title">
      <a href="#">
        {{ product.title }}
      </a>
    </h3>

    <span class="catalog__price">
      {{ product.price | numberFormat }} Р
    </span>

    <ul class="colors colors--black">
      <li class="colors__item" v-for="(col, index) in product.colors.length" :key="col.id"
        :style="{ backgroundColor: product.colors[index] }">
        <label class="colors__label" for="name">
          <input class="colors__radio sr-only" type="radio">
          <span class="colors__value">
          </span>
        </label>
      </li>
    </ul>
  </div>
</template>
<script>
import goToPage from '@/helpers/goToPage';
import numberFormat from '@/helpers/numberFormat';

export default {
  props: ['product'],
  filters: {
    numberFormat,
  },
  methods: {
    goToPage,
  },
};
</script>
