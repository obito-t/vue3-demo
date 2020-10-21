<template>
  <a-layout id="components-layout-demo-top-side">
    <a-layout-header class="header">
      <div class="logo" />
      <a-menu theme="dark"
        mode="horizontal"
        v-model:selectedKeys="selectedKeys1"
        :style="{ lineHeight: '64px' }">
        <a-menu-item key="/">
          <router-link to="/">首页</router-link>
        </a-menu-item>
        <a-menu-item key="/plan">
          <router-link to="/plan">时间计划</router-link>
        </a-menu-item>
      </a-menu>
    </a-layout-header>
    <a-layout-content style="padding: 0 50px">
      <!-- <a-breadcrumb style="margin: 16px 0">
        <a-breadcrumb-item>Home</a-breadcrumb-item>
        <a-breadcrumb-item>List</a-breadcrumb-item>
        <a-breadcrumb-item>App</a-breadcrumb-item>
      </a-breadcrumb> -->
      <a-layout style="padding: 24px 0; background: #fff">
        <!-- <a-layout-sider width="200"
          style="background: #fff">
          <a-menu mode="inline"
            v-model:selectedKeys="selectedKeys2"
            v-model:openKeys="openKeys"
            style="height: 100%">
            <a-sub-menu key="sub1">
              <template v-slot:title>
                <span>
                  <user-outlined />subnav 1
                </span>
              </template>
              <a-menu-item key="1">option1</a-menu-item>
              <a-menu-item key="2">option2</a-menu-item>
              <a-menu-item key="3">option3</a-menu-item>
              <a-menu-item key="4">option4</a-menu-item>
            </a-sub-menu>
            <a-sub-menu key="sub2">
              <template v-slot:title>
                <span>
                  <laptop-outlined />subnav 2
                </span>
              </template>
              <a-menu-item key="5">option5</a-menu-item>
              <a-menu-item key="6">option6</a-menu-item>
              <a-menu-item key="7">option7</a-menu-item>
              <a-menu-item key="8">option8</a-menu-item>
            </a-sub-menu>
            <a-sub-menu key="sub3">
              <template v-slot:title>
                <span>
                  <notification-outlined />subnav 3
                </span>
              </template>
              <a-menu-item key="9">option9</a-menu-item>
              <a-menu-item key="10">option10</a-menu-item>
              <a-menu-item key="11">option11</a-menu-item>
              <a-menu-item key="12">option12</a-menu-item>
            </a-sub-menu>
          </a-menu>
        </a-layout-sider> -->
        <a-layout-content :style="{ padding: '0 24px', minHeight: '280px' }">
          <router-view></router-view>
        </a-layout-content>
      </a-layout>
    </a-layout-content>
    <a-layout-footer style="text-align: center">
      Ant Design ©2018 Created by Ant UED
    </a-layout-footer>
  </a-layout>
</template>

<script>
import { computed, reactive, toRefs, watch } from "vue";
import { useRoute } from "vue-router";
export default {
  setup(props, context) {
    //context: atr,slots emit
    // 默认只执行一次
    const route = useRoute();
    const state = reactive({
      selectedKeys1: computed(() => [route.path]),
    });

    return {
      ...toRefs(state), //解构的同时保证数据响应式
    };
  },
};
</script>

<style>
#components-layout-demo-top-side .logo {
  width: 120px;
  height: 31px;
  background: rgba(255, 255, 255, 0.2);
  margin: 16px 28px 16px 0;
  float: left;
}
</style>
