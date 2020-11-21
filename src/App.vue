<template>
 <div class="container">
  <global-header :user="currentUser"></global-header>
  <column-list :list="list"></column-list>
 </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

import 'bootstrap/dist/css/bootstrap.min.css'
import ColumnList, { ColumnProps } from './components/ColumnList.vue'
import GlobalHeader, { UserProps } from './components/GlobalHeader.vue'
const currentUser: UserProps = {
  isLogin: true,
  name: 'jack'
}
const testData: ColumnProps[] = [
  {
    id: 1,
    title: 'test1的专栏',
    description: '测试',
    avatar: 'https://file02.16sucai.com/d/file/2014/0704/e53c868ee9e8e7b28c424b56afe2066d.jpg'

  },
  {
    id: 2,
    title: 'test1的专栏',
    description: '测试2',
    avatar: 'https://file02.16sucai.com/d/file/2014/0704/e53c868ee9e8e7b28c424b56afe2066d.jpg'

  },
  {
    id: 3,
    title: 'test3的专栏',
    description: '测试3'
    // avatar: 'https://file02.16sucai.com/d/file/2014/0704/e53c868ee9e8e7b28c424b56afe2066d.jpg'

  },
  {
    id: 3,
    title: 'test3的专栏',
    description: '测试3',
    avatar: 'https://file02.16sucai.com/d/file/2014/0704/e53c868ee9e8e7b28c424b56afe2066d.jpg'

  }
]
export default defineComponent({
  name: 'App',
  components: {
    ColumnList,
    GlobalHeader
  },
  setup () {
    return {
      list: testData,
      currentUser
    }
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
  margin-top: 60px;
}
</style>
