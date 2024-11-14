<template>
    <div class="card">
        <div class="card-db">
            <arrowRight/>
        <span class="title">{{ title }}</span>
        </div>
        <slot></slot>
    </div>
</template>
<script>
import arrowRight from './arrowRight.vue';
export default {
    name: 'Card',
    components:{
        arrowRight
    },
    props: {
        title: String,


    }
}
</script>

<style lang="scss" scoped>
.card {
    width: 100%;
    border-radius: 8px;
    // box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    border: 1px solid rgb(27, 168, 234);
    height: 100%;
    padding: 5px;
    .card-db{
        display: flex;
        align-items: center;
        height: 30px;
        width: 100%;
        .title {
        color: #fff;
        font-size: 18px;
        margin-left: 10px;
        font-weight: bold;
    }
    }

    
}
</style>