<template>
    <nav>
        <div class="logo"><div class="image"></div><h1>Player</h1></div>
        <ul>
            <li><NuxtLink to="/">Introducction</NuxtLink></li>
            <li><NuxtLink to="/foundations">Foundations</NuxtLink></li>
            <li><NuxtLink to="/tokens">Tokens</NuxtLink></li>
            <li><NuxtLink to="/components">Components</NuxtLink></li>
        </ul>
    </nav>
</template>
<script>
    export default {

    }
</script>
<style scope lang="scss">

    // Import Tokens
    @import '../../css/foundations/colors'; 
    @import '../../css/foundations/fonts'; 

    .logo{
        font-family: $font-family-clashDisplay;
        font-size: $font-size-subtitle-m;
        display: flex;
        flex-wrap: nowrap;
        align-items: center;
        gap: 12px;

        .image{
            position: relative;
            width: 28px;
            height: 18px;
            background-image: url("~/static/brand/logo.svg");
            background-position: center;
            background-size: 100%;
        }
    }
    nav{
        position: relative;
        width: 100%;
        height: auto;
        padding: 30px;
        display: flex;
        flex-wrap: nowrap;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;

        ul{
            display: flex;
            flex-wrap: nowrap;
            flex-direction: row;
            gap: 22px;

            li a{
                color: $color-lightScale-200;
                text-decoration: none;

                &:hover{
                    color: $color-light;
                }
                &.nuxt-link-exact-active {
                    color: $color-light;
                }
            }
        }
    }
</style>