<template>
    <div class="section-nav">
        <ul>
            <li v-for="(sec, index) in sectionNav" :key="index">
                <div v-if="!sec.sectionHome" class="sec-title" @click="openSub(index)">
                    <NuxtLink v-if="!sec.subSection" :to="'/' + titlePage + '/' + sec.sectionName | url">
                       {{ sec.sectionName }}
                   </NuxtLink>
                   <p v-else>{{ sec.sectionName }}</p>
                </div>
                <div v-else class="sec-title">
                    <NuxtLink :to="'/' + titlePage | url">
                        {{ sec.sectionName }}
                    </NuxtLink>
                </div>
                <div
                    class="sec-sub"
                    ref="subSection"
                    :class="{ open: isOpen === index }"
                    :style="{ height: isOpen === index ? subHeight + 'px' : 0 }"
                >
                    <ul ref="subItems">
                        <li v-for="(sub, index) in sec.subSection" :key="index">
                            <NuxtLink :to="'/' + titlePage + '/' + sub.subName | url">
                                <liIcon :section="sec.sectionName" :type="sub.subName" />
                                {{ sub.subName }}
                            </NuxtLink>
                        </li>
                    </ul>
                </div>
            </li>
        </ul>
    </div>
</template>
<script>
    // Import  Components
    import liIcon from "~/components/navigator/li-icon.vue";

    export default {
        components: {
            liIcon,
        },
        props: ['sectionNav', 'titlePage'],
        filters: {
            url: function (value) {
                if (!value) return ''
                value = value.toLowerCase().replace(/\s+/g, '-')
                return value;
            }
        },
        data() {
            return {
                isOpen: null,
                subHeight: 0,
            }
        },
        methods: {
            openSub(index) {

                console.log(index);

                if(this.isOpen === index) {
                    this.isOpen = null;
                } else {
                    this.isOpen = index;
                }

                if(this.isOpen !== null) {
                    var dropHeight = this.$refs.subItems[index].clientHeight;
                    this.subHeight = dropHeight;
                } else {
                    this.subHeight = "0";
                }
            },
        },
    }
</script>
<style scope lang="scss">

    // Import Tokens
    @import '../../css/foundations/colors'; 
    @import '../../css/foundations/fonts';

    .section-nav{
        width: 100%;
        height: auto;

        ul{
            position: relative;
            display: flex;
            flex-direction: column;
            flex-wrap: nowrap;
        }
        >ul{
            gap: 22px;

            li{
                .sec-title{
                    //margin-bottom: 8px;

                    a{
                        color: $color-lightScale-100;

                        &.nuxt-link-exact-active {
                            color: $color-light;
                        }
                    }
                    p{
                        cursor: pointer;
                    }
                }
                .sec-sub {
                    height: 0;
                    overflow: hidden;
                    transition: height ease-in-out .3s;
                
                    ul{
                        gap: 6px;
                        padding-top: 8px;

                        li  a{
                            color: $color-lightScale-200;
                            font-weight: $font-weight-200;
                            display: flex;
                            flex-direction: row;
                            flex-wrap: nowrap;
                            align-items: baseline;
                            gap: 4px;

                            .icon{
                                opacity: $opacity-40;
                            }

                            &.nuxt-link-exact-active {
                                color: $color-lightScale-100;

                                .icon{
                                    opacity: $opacity-70;
                                }
                            }
                        }
                    }
                }
            }
        }
    }

    .nuxt-link-exact-active {
        color: red;
    }

</style>