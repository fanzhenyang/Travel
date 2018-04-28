<template>
  <div id="app">
    <keep-alive>
      <router-view/>
    </keep-alive>
  </div>
</template>

<script>
// exclude = '组件名称' ，每次竟如该组件都会获取最新得数据 exclude="Detail"
export default {
  name: 'App'
}
</script>

<style>

</style>
