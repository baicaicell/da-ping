<template>
    <div class="card">
        <span class="title">{{ title }}</span>
        <slot></slot>
    </div>
</template>
<script>
export default {
    name: 'Card',
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
    border: 1px solid rgb(12, 108, 196);
    height: 100px;

    .title {
        color: #fff;
        font-size: 13px;
    }
}
</style>