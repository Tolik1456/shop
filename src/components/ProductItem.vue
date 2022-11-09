<template>
  <div>
    <router-link class="catalog__pic" :to="{name: 'product', params: {id: product.id}}">
      <img :src=product.image :alt=title>
    </router-link>

    <h3 class="catalog__title">
      <a href="#">
        {{ product.title }}
      </a>
    </h3>

    <span class="catalog__price">
      {{ product.price | numberFormat }} Р
    </span>

    <ul class="colors colors--black">
      <li class="colors__item" v-for="(col, index) in product.colors.length" :key="col.id">
        <label class="colors__label" for="name">
          <input class="colors__radio sr-only" type="radio">
          <span class="colors__value" :style="{ 'backgroundColor': `${product.colors[index]}`}">
          </span>
        </label>
      </li>
    </ul>
  </div>
</template>
<script>
import numberFormat from '@/helpers/numberFormat';

export default {
  props: ['product'],
  filters: {
    numberFormat,
  },
};
</script>
