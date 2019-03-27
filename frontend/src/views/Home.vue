<template>
  <div class="home">
    <TagsCloud/>
    <FilteredResults/>
  </div>
</template>

<script>
// @ is an alias to /src
import TagsCloud from "@/components/TagsCloud.vue";
import FilteredResults from "@/components/FilteredResults.vue";

export default {
  name: "home",
  components: {
    TagsCloud,
    FilteredResults
  }
};
</script>
