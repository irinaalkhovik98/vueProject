<template>
  <div class="v-cart-item">
    <img :src=" require('../assets/image/' + cart_item_data.image) " alt="img">
    <div class="v-cart-item_">
      <p>{{cart_item_data.name}}</p>
      <p>{{cart_item_data.price}}</p>
      <p>{{cart_item_data.article}} </p>
    </div>
    <div class="v-cart-item_quantity">
      <p>Qty:</p>
      {{cart_item_data.quantity}} </div>
    <button @click="deleteFromCart">Delete</button>
  </div>
</template>

<script>
export default {
  name: 'v-cart-item',
  props: {
    cart_item_data: {
      type: Object,
      default() {
        return {}
      }
    }
  },
  data() {
    return {}
  },
  computed: {},
  methods: {
    deleteFromCart() {
      this.$emit('deleteFromCart')
    }
  },
  mounted() {
    this.$set(this.cart_item_data, 'quantity', 1)
  }
}
</script>

<style lang="scss">
@import "../assets/styles/variables.scss";
  .v-cart-item {
    display: flex;
    flex-wrap: nowrap;
    justify-content: space-between;
    align-items: center;
    box-shadow: 0 0 10px 0 #e0e0e0;
    padding: $padding*2;
    margin-bottom: $margin*2;

    img {
      max-width: 50px;
    }
  }
</style>