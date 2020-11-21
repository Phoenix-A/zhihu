<template>
<div class="dropdown" >
  <a class="btn btn btn-outline-light dropdown-toggle" href="#" role="button" id="dropdownMenuLink" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false"  @click.prevent="toggleOpen">
    {{title}}
  </a>

  <div class="dropdown-menu" aria-labelledby="dropdownMenuLink" :style="{display: 'block'}" v-if="isOpen">
    <a class="dropdown-item" href="#">新建文章</a>
    <a class="dropdown-item" href="#">编辑资料</a>
    <a class="dropdown-item" href="#">滴滴滴</a>
  </div>
</div>

</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'
export default defineComponent({
  name: 'Dropdown',
  props: {
    title: {
      type: String,
      required: true
    }
  },
  setup () {
    const isOpen = ref(false)
    const toggleOpen = () => {
      isOpen.value = !isOpen.value
    }
    return {
      isOpen,
      toggleOpen
    }
  }
})
</script>
