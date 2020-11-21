<template>
  <nav class="navbar navbar-light justify-content-between mb-4 bg-primary">
   <a href="#" class="navbar-brand ">知乎专栏</a>
   <ul v-if="!user.isLogin" class="list-inline">
    <li class="list-inline-item"><a href="#" class="btn btn-outline-info my-2">登录</a></li>
    <li class="list-inline-item"><a href="#" class="btn btn-outline-light my-2">注册</a></li>
   </ul>
   <ul v-else class="list-inline">
        <li class="list-inline-item"><dropdown :title="`你好，${user.name}`"></dropdown></li>
   </ul>
</nav>

</template>
<script lang="ts">
import { defineComponent, PropType } from 'vue'
import Dropdown from './Dropdown.vue'

export interface UserProps {
  isLogin: boolean;
  name?: string;
  id?: number;
}
export default defineComponent({
  name: 'GlobalHeader',
  components: {
    Dropdown
  },
  props: {
    user: {
      type: Object as PropType<UserProps>,
      require: true
    }
  }
})
</script>
<style>
.navbar-light .navbar-brand{
  color:#ffffff;
  padding-left: 1rem;
}
.list-inline{
  padding-right: 1rem;
}
</style>
