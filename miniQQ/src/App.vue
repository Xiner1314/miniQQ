<template>
  <div id="app">
    <div class="content-top">
      <top-nav></top-nav>
    </div>
    <router-view/>
    <div class="tabbar">
      <bottom-tab></bottom-tab>
    </div>
    <!--聊天页面-->
    <chat-view v-if="chat"></chat-view>
    <!--侧边抽屉栏-->
    <SettingDrawer></SettingDrawer>
    <!--用户详情页面-->
    <detail-view v-if="showDetail"></detail-view>
    <!--搜索页面-->
    <SearchView v-if="showSearch"></SearchView>
  </div>
</template>

<script>
  import {mapState} from 'vuex'
  import TopNav from './components/topnav/TopNavigation'
  import BottomTab from './components/bottomTab/BottomTab'
  import ChatView from './components/chatView/ChatView'
  import SettingDrawer from './components/settingDrawer/SettingDrawer'
  import DetailView from './components/detailView/DetailView'
  import SearchView from './components/searchView/SearchView'

  export default {
    name: 'App',
    computed: mapState({allData: 'data', chat: 'chat', showDetail: 'showDetail', showSearch: 'showSearch'}),
    components: {
      TopNav,
      BottomTab,
      ChatView,
      DetailView,
      SearchView,
      SettingDrawer
    }
  }
</script>

<style>
  .tabbar {
    position: fixed;
    bottom: 0;
    left: 0;
    width: 100%;
  }
</style>
