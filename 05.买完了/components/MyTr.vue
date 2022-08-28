<template>
  <div>
    <table>
      <tr>
        <td><input type="number" v-model="obj['count']"></td>
        <td>
          <span>{{obj['goodsName']}}</span>
        </td>
        <td>
          <span v-show="obj['count'] == 0">卖光了</span>
        </td>
      </tr>
    </table>
  </div>
</template>

<script>
  export default {
    props: ['obj'],
    data() {
      return {
        number: ''
      }
    },
  }
</script>

<style scoped>

</style>