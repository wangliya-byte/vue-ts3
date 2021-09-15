<template>
    <nav class="navbar navbar-dark bg-primary justify-content-between mb-4 px-4">
        <a class="navbar-brand" href="#">知之为知之</a>
        <ul v-if="!user.isLogin" class="nav">
            <li class="nav-item">
                <a class="btn btn-outline-light my-2 mx-2" href="#">登录</a>
            </li>
            <li class="nav-item">
                <a class="btn btn-outline-light my-2 mx-2"  href="#">注册</a>
            </li>
        </ul>
        <ul v-if="user.isLogin" class="nav">
            <li class="list-line-item">
                <drop-down :title="`hello,${user.name}`"></drop-down>
            </li>
        </ul>
    </nav>
</template>
<script lang='ts'>
import { defineComponent, PropType, ref } from 'vue'
import dropDown from './dropDown.vue'
export interface UserProps {
    id?:number,
    name?:string,
    isLogin:boolean
}
export default defineComponent({
  name: 'header',
  props: {
    user: {
      type: Object as PropType<UserProps>,
      required: true
    }
  },
  components: {
    dropDown
  }
//   setup (props) {
//     const title = ref(props.user.name)
//     return {
//       title
//     }
//   }
})
</script>
