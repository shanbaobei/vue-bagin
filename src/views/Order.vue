<template>
    <div>
        <div class="left">
      左侧下单
      <ul>
        <li v-for="(item,index) in lists" :key="'order'+ index">
          <span>{{item.name}}-{{item.url}}-{{item.type}}-{{item.price}}</span>
          <button type="button" @click="minus
            (item,index)">-</button>
          <span>
            {{typeof item.num === 'undefined'
            ? 0: item.num}}
          </span>
          <button type="button" @click="add(item,index)">+</button>
        </li>
      </ul>
    </div>
     <div class="right">
      计算部分
      <!-- <ul>
        <li v-for="(item,index) in orders"
        :key="'order' + index">
        菜品名称:{{item.name}}-菜品单价:{{
          item.price}}-单项总价:{{item.price
          * item.num}}
          </li>
      </ul>
      <p>菜单总价:{{total}}</p>-->
    </div>
    </div>
</template>
<script>
export default {
  name: 'order',
  data () {
    return {
      lists: this.$store.state.lists

    }
  },
  computed: {
    orders () {
      return _.filter(this.lists, (item) =>
        typeof item.num !== 'undefined' &&
      item.num > 0)
    },
    methods: {
      minus (item, index) {
        if (typeof item.num === 'undefined') {
          item.num = 0
        }
        item.num--
        if (item.num < 0) {
          item.num = 0
        }
      },
      add (item, index) {
        if (typeof item.num === 'undefined') {
          item.num = 0
        }
        item.num++
        if (item.num > 0) {
          item.num = 100
        }
      }
    }
  }
}
</script>
<style lang="sass" scoped>

</style>
