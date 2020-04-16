<template>
  <div class="cartcontrol">
    <transition name="move">
      <div
        class="cart-decrease icon-remove_circle_outline"
        v-show="food.count>0"
        @click="decreaseCart($event)"
      >
        <transition name="rotate">
          <span class="inner icon-remove_circle_outline" v-show="food.count>0"></span>
        </transition>
      </div>
    </transition>
    <div class="cart-count" v-show="food.count>0">{{food.count}}</div>
    <div class="cart-add icon-add_circle" @click="addCart($event)"></div>
  </div>
</template>

<script type="text/ecmascript-6">
/* eslint-disable */
import Vue from "vue";
export default {
  props: {
    food: {
      type: Object
    }
  },
  created() {
    // console.log(this.food);
  },
  methods: {
    addCart(event) {
      if (!event._constructed) {
        return;
      }
      if (!this.food.count) {
        Vue.set(this.food, "count", 1);
      } else {
        this.food.count++;
      }
      console.log(this.food.count);
    },
    decreaseCart(event) {
      if (!event._constructed) {
        return;
      }
      if (!this.food.count) {
        Vue.set(this.food, "count", 1);
      } else {
        this.food.count--;
      }
      console.log(this.food.count);
    }
  }
};
</script>

<style lang="stylus">
.cartcontrol {
  font-size: 0;

  .cart-decrease {
    display: inline-block;
    padding: 6px;
    transition: all 0.4s linear;

    .inner {
      display: inline-block;
      line-height: 24px;
      color: rgb(0, 160, 220);
      font-size: 24px;
      transition: all 0.4s linear;

      &.rotate-transition {
        transform: rotate(0);
      }

      &.rotate-enter, &.rotate-leave {
        transform: rotate(180deg);
      }
    }

    &.move-transition {
      opacity: 1;
      transform: translate3d(0, 0, 0);
    }

    &.move-enter, &.move-leave {
      opacity: 0;
      transform: translate3d(24px, 0, 0);
    }
  }

  .cart-count {
    display: inline-block;
    font-size: 10px;
    vertical-align: top;
    width: 12px;
    padding-top: 6px;
    line-height: 24px;
    color: rgb(147, 153, 159);
  }

  .cart-add {
    display: inline-block;
    font-size: 24px;
    padding: 6px;
    line-height: 24px;
    color: rgb(0, 160, 220);
  }
}
</style>
