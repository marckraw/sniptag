<template>
  <div class="home">
    <TagsCloud/>
  </div>
</template>

<script>
// @ is an alias to /src
import TagsCloud from "@/components/TagsCloud.vue";

export default {
  name: "home",
  components: {
    TagsCloud
  }
};
</script>
