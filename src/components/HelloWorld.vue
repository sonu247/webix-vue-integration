<template>
  <div class="hello">
    <WebixUi :config="ui" />
  </div>
</template>

<script>
import WebixUi from "./../WebixUi.vue";
export default {
  name: "HelloWorld",
  components: { WebixUi },
  props: {
    msg: String,
  },
  data: () => ({
    ui: {
      id: "pivot",
      view: "pivot",
      height: window.innerHeight,
      separateLabel: true,
      max: true,
      structure: {
        rows: ["form", "name"],
        columns: ["year"],
        values: [
          { name: "gdp", operation: "sum" },
          { name: "oil", operation: "sum" },
        ],
        filters: [{ name: "name", type: "select" }],
      },
      url: "/data.json",
    },
  }),
};
</script>
