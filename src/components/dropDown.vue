<template>
    <div class="dropdown">
        <a class="btn btn-outline-light my-2 mx-2 dropdown-toggle" @click.prevent="toggleDrop">{{title}}</a>
        <ul class="dropdown-menu" aria-labelledby="dropdownMenuButton1" v-if="isOpen" :style="{display:'block'}">
            <li><a class="dropdown-item" href="#">Action</a></li>
            <li><a class="dropdown-item" href="#">Another action</a></li>
        </ul>
    </div>
</template>
<script lang ='ts'>
import { defineComponent, ref } from 'vue'

export default defineComponent({
  props: {
    title: {
      type: String,
      required: true
    }
  },
  setup () {
    const isOpen = ref(false)
    const toggleDrop = () => {
      isOpen.value = !isOpen.value
    }
    return {
      isOpen,
      toggleDrop
    }
  }
})
</script>
