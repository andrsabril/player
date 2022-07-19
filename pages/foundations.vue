<template>
  <div>
    <div class="main-structure">
      <div class="main-sub-menu">
        <SectionNav :sectionNav="sectionNav" :titlePage="titlePage" />
      </div>
      <div class="main-ctn">
        <NuxtChild />          
      </div>
    </div>
  </div>
</template>

<script>
// Import  Components
import SectionNav from "~/components/navigator/section-nav.vue";

export default {
  components: {
    SectionNav,
  },
  data() {
      return {
        titlePage: "Foundations",
        sectionNav: [
          {
            sectionName: "About Player",
            sectionHome: true,
            subSection: null,
          },
          {
            sectionName: "Colors",
            sectionHome: false,
            subSection: [
              { subName: "Brand" },
              { subName: "Opacity" },
              { subName: "Gradient" },
            ],
          },
        ],
      }
    },
}
</script>
<style scoped lang="scss">

  // Import Tokens
  @import '../css/foundations/colors'; 
  @import '../css/foundations/fonts'; 

</style>
