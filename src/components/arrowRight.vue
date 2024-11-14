<template>
    <div class="arrow-right">
            <div class="arrow-right-ls"></div>
            <div class="arrow-right-qls"></div>
        </div>
</template>
<script>
export default{

}
</script>
<style scoped lang="scss">
.arrow-right {
        display: flex;

        .arrow-right-ls {
            /* 设置盒子的宽和高 */
            width: 20px;
            height: 20px;
            /* 添加边框颜色，以及边框样式为实线*/
            border: rgb(75, 150, 243) solid;
            /* 只添加上边框和右边框 ，下边框和左边框为0*/
            border-width: 10px 10px 0 0;
            /* 旋转45度 */
            transform: rotate(45deg);
        }

        .arrow-right-qls {
            /* 设置盒子的宽和高 */
            width: 20px;
            height: 20px;
            /* 添加边框颜色，以及边框样式为实线*/
            border: rgb(148, 210, 77) solid;
            /* 只添加上边框和右边框 ，下边框和左边框为0*/
            border-width: 10px 10px 0 0;
            /* 旋转45度 */
            transform: rotate(45deg);
        }
    }
</style>