<template>
  <div>
    <p>标题</p>
    <input type="text" v-model="title">
    <p>内容</p>
    <input type="text" v-model="content">
    <div class="button" @click="add()">添加</div>
  </div>
</template>

<script>
    import store from '@/store'
    export default {
        name: 'add',
        data () {
            return {
                title: '',
                content: ''
            }
        },
        methods: {
            add() {
                store.commit('addItems',{
                    titile: this.title,
                    content: this.content
                })
                this.title = '';
                this.content = '';
                this.$router.push('/home/list');
            }
        }
    }
</script>

