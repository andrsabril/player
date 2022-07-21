<template>
    <div class="icon" :class="section + '-' + type | url">
        <img :src="'@/static/img/icons/' + section + '-' + type + '.svg' | url">
    </div>
</template>
<script>
    export default {
        props: ['type', 'section'],
        filters: {
            url: function (value) {
                if (!value) return ''
                value = value.toLowerCase().replace(/\s+/g, '-')
                return value;
            }
        },
    }
</script>
<style scoped lang="scss">
    .icon{
        width: 16px;
        height: 16px;

        img{
            width: 100%;
            height: 100%;
        }
    }
</style>