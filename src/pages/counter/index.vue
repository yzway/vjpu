<template>
  <div class="counter-warp">
    <p>Vuex counter：{{ getCount }}</p>
    <p>
      <van-button plain type="primary" @click="increment">+</van-button>
      <van-button disabled type="info" @click="decrement">-</van-button>
      <br/>
      <br/>
      <van-button round loading type="default" size="large" loading-text="正在请求数据" color="#7232dd" plain />
    </p>
    <mp-date
      @onConfirm="objk"
      :unit="false"
      key-name="zhuangbikey"
    />
  </div>
</template>

<script>
    import {mapGetters, mapMutations} from 'vuex'
    import mpDate from '../index/mpDate'
    // import {mapState} from 'vuex'

    export default {
      components: {mpDate},
      computed: {
        ...mapGetters(['getCount'])

        // getCount () {
        // console.log(this.myText)
        // return this.zb.getters.getCount
        // return this.myText
        // }
        // ...mapState({
        //   myText: 'text'
        // })
      },
      methods: {
        ...mapMutations(['increment', 'decrement']),
        objk ({value, keyName, time}) {
          console.log(value + '\n' + keyName + '\n' + time)
        }
        // increment () {
        //   return this.zb.commit('increment')
        // },
        // decrement () {
        //   return this.zb.commit('decrement')
        // }
      }
    }
</script>

<style>
  .counter-warp {
    text-align: center;
    margin-top: 100px;
  }

  .home {
    display: inline-block;
    margin: 100px auto;
    padding: 5px 10px;
    color: blue;
    border: 1px solid blue;
  }
</style>
