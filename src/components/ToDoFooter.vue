<template>
    <div class="todo_footer_container">
        <div class="footer_container">
            <span>合计：2</span>
            <span>清空任务</span>
        </div>
    </div>
</template>

<script>
export default {

}
</script>

<style lang="less" scoped>
.todo_footer_container {
    width: 500px;
    margin: 0 auto;

    .footer_container {
        display: flex;
        justify-content: space-between;
        width: 328px;
        height: 40px;
        line-height: 40px;
        margin: 0 auto;
        background-color: #fff;
        font-size: 12px;
        padding: 0px 10px;
        color: #a5a3a3;

    }
}
</style>