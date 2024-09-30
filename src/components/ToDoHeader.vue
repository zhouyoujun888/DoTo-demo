<template>
    <div class="todo_header_container">
        <h1 class="todo_title">宥宥记事本</h1>
        <div class="ipt_container">
            <input v-model="todoName" @keyup.enter="handelAdd" class="ipt_todo" type="text" placeholder="输入待办事项">
            <button @click="handelAdd" class="ipt_btn">添加任务</button>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            todoName: ''
        }
    },
    methods: {
        handelAdd() {
            if (!this.todoName) {
                return alert('输入不能为空')
            }
            this.$emit('addTodoName', this.todoName)
            // 每次调用就清空输入框的值
            this.todoName = ''
        }
    }
}
</script>

<style lang="less" scoped>
.todo_header_container {
    width: 500px;
    margin: 0 auto;

    .todo_title {
        color: aqua;
        text-align: center;
    }

    .ipt_container {
        display: flex;
        justify-content: center;

        .ipt_todo {
            padding-left: 5px;
            margin: 0;
            width: 240px;
            height: 50px;
            line-height: 50px;
            color: #ccc;
            border: 1px solid aqua;
            border-right: none;
            outline: none;
            border-radius: 10px 0px 0px 0px;
            font-size: 16px;

            &::placeholder {
                color: #ccc;
            }
        }


        .ipt_btn {
            width: 100px;
            height: 54px;
            font-size: 16px;
            line-height: 48px;
            border: 1px solid aqua;
            border-radius: 0px 10px 0px 0px;
            background-color: aqua;
            color: #fff;
        }
    }
}
</style>