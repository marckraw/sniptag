<template>
  <div class="tags-cloud">
    <button v-on:click="clickMe">Click me!</button>
    <Tag v-for="tag in tags" :key="tag.id" :data="tag"/>
  </div>
</template>

<script>
import Tag from "./Tag";

export default {
  name: "tags-cloud",
  data: () => ({
    tags: [
      { id: 0, name: "javascript", label: "javascript" },
      { id: 1, name: "css", label: "css" },
      { id: 2, name: "python", label: "python" },
      { id: 3, name: "dev ops", label: "dev_ops" }
    ]
  }),
  methods: {
    clickMe() {
      console.log("clicking me!");
    }
  },
  components: {
    Tag
  },
  //   props: {
  //         'lyMarkers': { type: Array, required: true },
  //         'lyInfoOpened': { type: Boolean, default: false },
  //     },
  mounted() {
    console.log("TagsCloud mounted");
    console.log(this.tags);
  }
};
</script>

<style>
</style>
