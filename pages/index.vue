<template>
  <NotionRenderer :blockMap="blockMap" fullPage />
</template>

<script>
export default {
  data: () => ({ blockMap: null }),
  async asyncData({ $notion }) {
    // use Notion module to get Notion blocks from the API via a Notion pageId
    const blockMap = await $notion.getPageBlocks(
      "c48f8bf1b2214423b1ce9014010c832c" // Paste your Notion page ID here
    );
    return { blockMap };
  },
};
</script>

<style>
@import "vue-notion/src/styles.css"; /* optional Notion-like styles */ 
</style>