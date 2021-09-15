<template>
  <div class="">
    <div class="container">
      <div class="row">
      <div v-for="colum in list" :key="colum.id" class="col-4 mb-4">
        <div class="card shadow-sm">
          <div class="card-body text-center">
            <img :src="colum.avatar" class="card-img-top" alt="...">
            <h5 class="card-title">{{colum.title}}</h5>
            <p class="card-text text-left">{{colum.description}}}</p>
            <a href="#" class="btn btn-outline-primary">进入</a>
          </div>
        </div>
      </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue'
export interface ColumProps {
  id:number,
  avatar?:string,
  title:string,
  description:string
}
export default defineComponent({
  name: 'columlist',
  props: {
    list: {
      type: Array as PropType<ColumProps[]>,
      required: true
    }
  },
  setup (props) {
    props.list.map((e) => {
      if (!e.avatar) {
        e.avatar = require('../assets/imgs/column.jpg')
      }
    })
    return props.list
    // const list: ColumList[] = props.list
    // return {
    //   list
    // }
  }
})
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
