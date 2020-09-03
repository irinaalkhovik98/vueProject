<template>
  <div class="v-catalog-item">
    <img class="v-catalog_item_img" :src=" require('../assets/image/' + product_data.image) " alt="img">
    <p class="catalog_item_name">{{product_data.name}}</p>
    <p class="catalog_item_price">Price: {{product_data.price}} $</p>
    <button 
      class="catalog_item_add_to_cart_btn btn" 
      @click="addToCart">add to cart</button>
  </div>
</template>

<script>
  export default {
    name: 'v-catalog-item',
    components: {},
    props: {
      product_data: {
        type: Object,
        default() {
          return {}
        }
      }
    },
    data() {
      return {
      }
    },
    computed: {},
    methods: {
      addToCart() {
        this.$emit('addToCart', this.product_data)
      }
    },
    watch: {},
    mounted() {
      
    }
  }
</script>

<style lang="scss">
@import "../assets/styles/variables.scss";
  .v-catalog-item {
    flex-basis: 25%;
    box-shadow: 0 0 10px 0 #e0e0e0;
    padding: $padding*2;
    margin-bottom: $margin*2;
    border: 1px solid #aaa;
    img {
      width: 100px;
    }
  }
</style>