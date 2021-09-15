<template>
  <div>
    <Header :user="userList"></Header>
    <colum-list :list="testData"></colum-list>
  </div>
</template>
<script lang='ts'>
import 'bootstrap/dist/css/bootstrap.min.css'
import { defineComponent, reactive, ref } from 'vue'
import ColumList, { ColumProps } from './components/ColumList.vue'
import Header, { UserProps } from './components/header.vue'
const testData:ColumProps[] = [{
  id: 1,
  title: 'test1的专栏',
  description: '这是的test1专栏，有一段非常有意思的简介，可以更新一下欧, 这是的test1专栏，有一段非常有意思的简介，可以更新一下欧'
  // avatar: 'http://vue-maker.oss-cn-hangzhou.aliyuncs.com/vue-marker/5ee22dd58b3c4520912b9470.jpg?x-oss-process=image/resize,m_pad,h_150,w_150'
},
{
  id: 2,
  title: 'test2的专栏',
  description: '这是的test2专栏，有一段非常有意思的简介，可以更新一下欧',
  avatar: 'http://vue-maker.oss-cn-hangzhou.aliyuncs.com/vue-marker/5ee22dd58b3c4520912b9470.jpg?x-oss-process=image/resize,m_pad,h_100,w_100'
},
{
  id: 3,
  title: 'test3的专栏',
  description: '这是的test1专栏，有一段非常有意思的简介，可以更新一下欧 这是的test1专栏，有一段非常有意思的简介，可以更新一下欧',
  avatar: 'http://vue-maker.oss-cn-hangzhou.aliyuncs.com/vue-marker/5ee22dd58b3c4520912b9470.jpg?x-oss-process=image/resize,m_pad,h_100,w_100'
},
{
  id: 4,
  title: 'test4的专栏',
  description: '这是的test2专栏，有一段非常有意思的简介，可以更新一下欧',
  avatar: 'http://vue-maker.oss-cn-hangzhou.aliyuncs.com/vue-marker/5ee22dd58b3c4520912b9470.jpg?x-oss-process=image/resize,m_pad,h_100,w_100'
}]
const userList:UserProps = {
  id: 111,
  name: 'wly',
  isLogin: true
}
export default defineComponent({
  name: 'App',
  setup () {
    const a = ref(0)
    const b = reactive({ name: 'wly', age: 18 })
    // var b = new Proxy(b, hander)
    console.log('aaaaaaa==ref', a, b)
    return {
      testData,
      userList,
      a
    }
  },
  components: {
    ColumList,
    Header
  }
})
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
