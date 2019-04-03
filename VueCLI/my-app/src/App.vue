<template>
  <div id="app">
            {{msg}}
            <div>
                <input type="text" v-model="info">
                <!--Vue事件绑定-->
                <button @click="handleClick">添加</button>
            </div>
            <ul>
                <todo-item v-for="item in list" :key="item">
                    <template v-slot:item="itemProps">
                      <span v-solt:item :style="{fontSize: '20px',color: itemProps.checked ? 'red':'blue'}">{{item}}</span>
                    </template>
                </todo-item>
            </ul>
        </div>
</template>

<script>
import TodoItem from './components/TodoItem.vue'
export default {
  name: 'app',
  components: {
    TodoItem,
  },
  data(){
    return {
      msg: 'hello Vue',
      info: '',
      list: [],
    }
  },
  methods: {
    handleClick(){
      this.list.push(this.info)
      this.info = ''
    }
  }
}
</script>

<style>

</style>
