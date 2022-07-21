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
            sectionName: "About Foundations",
            sectionHome: true,
            subSection: null,
          },
          {
            sectionName: "Brand",
            sectionHome: false,
            subSection: [
              { subName: "Id" },
            ],
          },
          {
            sectionName: "Color",
            sectionHome: false,
            subSection: [
              { subName: "Generic" },
              { subName: "Gradient" },
              { subName: "Specific" },
            ],
          },
          {
            sectionName: "Type",
            sectionHome: false,
            subSection: null,
          },
          {
            sectionName: "Icons",
            sectionHome: false,
            subSection: [
              { subName: "Base" },
              { subName: "Flag" },
            ],
          },
          {
            sectionName: "Grid",
            sectionHome: false,
            subSection: [
              { subName: "Desktop" },
              { subName: "Tablet" },
              { subName: "Mobile" },
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
