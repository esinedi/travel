<template>
  <div class="recommend">
    <div class="recommend-title">热销推荐</div>
    <ul class="ul-main">
      <li class="item"
        v-for="item in recommendList"
        :key="item.id"
        @click="handleDetail(item.id)"
      >
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl" alt="">
        </div>
        <div class="item-info">
          <p class="item-title">{{ item.title }}</p>
          <p class="item-desc">{{ item.desc }}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    recommendList: Array
  },
  methods: {
    handleDetail (id) {
      this.$router.push('/detail/' + id)
    }
  }
}
</script>

<style lang="less" scoped>
.recommend-title {
  margin-top: .2rem;
  line-height: .8rem;
  background: #eee;
  text-indent: .2rem;
}
.ul-main {
  .item {
    display: flex;
    height: 1.9rem;
    overflow: hidden;
    border-bottom: 1px solid #eee;
    .item-img {
      width: 1.7rem;
      height: 1.7rem;
      padding: .1rem;
    }
    .item-info {
      flex: 1;
      padding: .1rem;
      min-width: 0;
      .item-title {
        line-height: .54rem;
        font-size: .32rem;
        .ellipsis();
      }
      .item-desc {
        line-height: .4rem;
        color: #ccc;
        .ellipsis();
      }
      .item-button {
        margin-top: .2rem;
        background: #ff9300;
        padding: 0 .2rem;
        border-radius: .06rem;
        color: #fff;
        line-height: .44rem;
      }
    }
  }
}
</style>
