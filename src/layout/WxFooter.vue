<template>
  <div id="wx-nav">
    <nav>
      <router-link  v-for="(item,index) in navMenu" :key="index" :to="item.to" tag="dl">
        <dt class="iconfont" :class="item.icon">
          <i class="new-msg-count" v-if="item.to==='/wechat'" v-show="$store.getters.newMsgCount>0">{{ $store.getters.newMsgCount }}</i>
          <i class="new-msg-dot" v-if="item.to==='/explore'" v-show="item.msgNum"></i>
          <i class="new-msg-count" v-else v-show="item.msgNum">{{ item.msgNum }}</i>
        </dt>
        <dd>{{ item.name }}</dd>
      </router-link>
    </nav>
  </div>
</template>
<script type="text/ecmascript-6">
  export default {
    data() {
      return {
        navMenu: [
          {
            name: '微信',
            to: '/wechat',
            icon: 'icon-wechat',
            msgNum: null
          },
          {
            name: '通讯录',
            to: '/addresslist',
            icon: 'icon-contact',
            msgNum: 1
          },
          {
            name: '发现',
            to: '/explore',
            icon: 'icon-find',
            msgNum: 1
          },
          {
            name: '我',
            to: '/self',
            icon: 'icon-me',
            msgNum: null
          },
        ]
      }
    },
    mounted() {

    }
  }
</script>
<style lang="less">
  @import "../assets/less/wx-nav.less";
</style>
