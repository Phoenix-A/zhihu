<template>
<div class="row ">
  <div v-for="column in columnList" :key="column.id" class="col-4 mb-3">
  <div class="card h-100 shadow-sm text-center ">
      <div class="card-body ">
      <img :src="column.avatar" class="card-img-top rounded-circle border-light w-25 " :alt="column.title">
      <h5 class="card-title">{{column.title}}</h5>
      <p class="card-text">{{column.description}}</p>
      <a href="#" class="btn btn-primary">进入专栏</a>
    </div>
  </div>

  </div>
</div>
</template>
<script lang="ts">
import { computed, defineComponent, PropType } from 'vue'
export interface ColumnProps {
  id: number;
  title: string;
  avatar?: string;
  description: string;
}
export default defineComponent({
  name: 'ColumnList',
  props: {
    list: {
      type: Array as PropType<ColumnProps[]>,
      required: true
    }
  },
  setup (props) {
    const columnList = computed(() => {
      return props.list.map((column) => {
        if (!column.avatar) {
          column.avatar = require('@/assets/logo.png')
        }
        return column
      })
    })
    return {
      columnList
    }
  }
})
</script>
