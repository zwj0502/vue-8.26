<template>
  <div>
    <table>

      <tr is="myTr" v-for="(item, index) in goodsArr" :key="index" :obj="item" :index="index"></tr>
    </table>
    <p>All Number:{{sumnumber }}</p>
  </div>
</template>

<script>
  import MyTr from '@/components/MyTr.vue'

  export default {
    components: {
      MyTr,
    },
    data() {
      return {
        goodsArr: [
          {
            count: 0,
            goodsName: "Watermelon"
          }, {
            count: 0,
            goodsName: "Banana"
          }, {
            count: 0,
            goodsName: "Orange"
          }, {
            count: 0,
            goodsName: "Pineapple"
          }, {
            count: 0,
            goodsName: "Strawberry"
          }
        ]
      }
    },
    computed: {
      sumnumber() {
        return this.goodsArr.reduce((sum, obj) => sum += obj.count * 1, 0)
      }
    }
  }
</script>

<style scoped>

</style>