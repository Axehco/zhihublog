<template>
  <div>
    <ul>
      <li v-for="c in list" :key="c.id">
        <img :src="c.avatar" :alt="c.title" />
        <h5>{{c.title}}</h5>
        <p>{{c.description}}</p>
        <a href="#">进入专栏</a>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue'
export interface ColumnProps {
  id: number
  title: string
  avatar: string
  description: string
}

export default defineComponent({
  name: 'ColumnList',
  props: {
    list: {
      type: Array as PropType<ColumnProps[]>, // 构造函数断言为一个类型
      required: true
    }
  }
})
</script>
