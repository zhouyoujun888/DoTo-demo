<template>
    <div class="todo_main_container">
        <ul>
            <li v-for="(item, index) in list" :key="item.id">
                <span>{{ (index + 1) + '.' + item.content }}</span>
                <span @click="handelDel(item.id)">X</span>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    props: {
        list: Array
    },
    methods: {
        handelDel(id) {
            this.$emit('delTodoName', id)
        }
    }
}
</script>

<style lang="less" scoped>
.todo_main_container {
    width: 500px;
    margin: 0 auto;

    ul {
        width: 348px;
        margin: 0 auto;
        padding: 0;
        list-style: none;
        color: #888585;
        background-color: #fff;

        li {
            display: flex;
            justify-content: space-between;
            padding: 6px;
            border-bottom: 1px solid #efe9e9;
            height: 34px;
            line-height: 34px;
        }
    }
}
</style>