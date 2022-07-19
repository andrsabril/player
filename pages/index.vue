<template>
  <div>
    <div class="structure">
      <div class="sub-menu">
          <SectionNav :sectionNav="sectionNav" :titlePage="titlePage" />
      </div>
      <div class="main-ctn">
        <div class="item" v-for="(docItem, index) in documentation" :key="docItem.index">
          <DocItem :docItem="docItem" :index="index" />
        </div>
      </div>
      <div class="ref-menu"></div>
    </div>
  </div>
</template>

<script>
// Import  Components
import DocItem from "~/components/doc-item.vue";
import SectionNav from "~/components/navigator/section-nav.vue";

export default {
  components: {
    DocItem,
    SectionNav,
  },
  data() {
      return {
        titlePage: "",
        sectionNav: [
          {
            sectionName: "About Player",
            sectionHome: true,
            subSection: false,
          },
          {
            sectionName: "Get Start",
            sectionHome: false,
            subSection: [
              { subName: "For Designers" },
              { subName: "For Dev" },
            ],
          },
          {
            sectionName: "Get Start 2",
            sectionHome: false,
            subSection: [
              { subName: "For Designers" },
              { subName: "For Dev" },
              { subName: "For Players" },
            ],
          },
        ],
        documentation: [
          {
            type: "text",
            title: "About Player",
            description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Adipiscing sit aliquet sit dolor. Sed eu neque purus et eu pulvinar. Felis risus, velit rutrum adipiscing tristique. Tempor suspendisse donec eget ipsum, sem vitae aliquet amet, dolor. Consequat nibh non blandit tristique eleifend etiam a. Vestibulum eu, sodales placerat id diam proin. Est enim diam nisl praesent viverra.",
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

  .structure{
    width: calc(100% - 60px);
    max-width: 1500px;
    margin: 0 auto;
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
    align-items: flex-start;
    justify-content: center;
    padding: 60px 0;

    .sub-menu, .ref-menu{
      width: 200px;
      height: auto;
    }
    .main-ctn{
      width: calc(100% - (200px * 2));
      height: auto;

      .item{
        margin-bottom: 60px;
      }
    }
  }
</style>
