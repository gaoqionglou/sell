<template>
  <div class="seller">
    <div class="seller-content">
      <div class="overview">
        <h1 class="title"></h1>
        <star :size="36" :score="seller.score"></star>
        <span class="text">({{seller.ratingCount}})</span>
        <span class="text">{{seller.sellerCount}}</span>
      </div>
      <ul class="remark">
        <li class="block">
          <h2>起送价</h2>
          <div class="content">
            <span class="stress">{{seller.minPrice}}</span>元
          </div>
        </li>
        <li class="block">
          <h2>商家配送</h2>
          <div class="content">
            <span class="stress">{{seller.deliveryPrice}}</span>元
          </div>
        </li>
        <li class="block">
          <h2>平均配送时间</h2>
          <div class="content">
            <span class="stress">{{seller.deliveryTime}}</span>元
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
/* eslint-disable */
import star from "../../components/star/star";
export default {
  components: { star },
  props: {
    seller: {
      type: Object,
      default() {
        return {};
      }
    }
  }
};
</script>

<style lang="stylus">
@import '../../common/stylus/mixin.styl';

.seller {
  position: absolute;
  top: 174px;
  bottom: 0;
  width: 100%;
  overflow: hidden;

  .overview {
    // position relative
    padding: 18px;
    .title{
      margin-bottom: 8px
      
    }
  }
}
</style>
