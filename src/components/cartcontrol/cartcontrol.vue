<template>
  <div class="cartcontrol">
    <div class="cart-decrease icon-remove_circle_outline" v-show="food.count>0" @click="decreaseCart"></div>
    <div class="cart-count" v-show="food.count>0">{{food.count}}</div>
    <div class="cart-add icon-add_circle" @click="addCart"></div>
  </div>
</template>

<script type="text/ecmascript-6">
  import Vue from 'vue';

  export default {
    name: "cartcontrol",
    props: {
      food: {
        type: Object
      }
    },
      methods: {
        addCart(event) {
          if (!event._constructed) {
            return;
          }
          if (!this.food.count) {
            Vue.set(this.food, 'count', 1);
          } else {
            this.food.count++;
          }
        },
        decreaseCart(event) {
          if (!event._construct) {
            return;
          }
          if (this.food.count) {
            this.food.count--;
          }
      }
    }
  };
</script>

<style lang="stylus" rel="stylesheet/stylus">
  .cartcontrol
    font-size: 0
      .cart-decrease, .cart-add
        display: inline-block
        padding: 6px
        line-height: 24px
        font-size: 24px
      .cart-count
        display: inline-block
        vertical-align: top
        width: 12px
        padding-top: 6px
        line-height: 24px
        text-align: center
        font-size: 10px
        color: rgb(147, 153, 150)
      .cart-add
        display: inline-block
</style>
