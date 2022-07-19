<template>
    <div :class="[docItem.type, index]">
        <h4> {{ docItem.title }}</h4>
        <p>{{ docItem.description }}</p>
    </div>
</template>
<script>
    export default {
        props: ['docItem'],
    }
</script>
<style scope lang="scss">

    // Import Tokens
    @import '../css/foundations/colors'; 
    @import '../css/foundations/fonts'; 

    .text{
        h4{
            font-size: $font-size-subtitle-s;
            font-weight: $font-weight-400;
        }
        p, h4{
            margin-bottom: 16px;
        }
        :nth-last-child{
            margin-bottom: 0;
        }
  }
</style>