<template>
  <div class="home">
    <Header title="whatever" :description="description" />
    <TagsCloud />
    <FilteredResults />
    <div>
      <h1></h1>
    </div>

    <transition name="fade">
      <h1 v-if="show">Animated</h1>
    </transition>
    <button @click="show = !show">shoow/hide</button>
  </div>
</template>

<script>
import TagsCloud from "@/components/TagsCloud.vue";
import FilteredResults from "@/components/FilteredResults.vue";
import Header from "@/components/Header.vue";

export default {
  name: "Home",
  data() {
    return {
      show: false,
      title: "some title",
      description: "asdlsjkdnfkjsadnfglksdjnlfkjndslk"
    };
  },
  beforeCreate() {
    console.log("beforeCreate lifecycle hook");
  },
  components: {
    TagsCloud,
    FilteredResults,
    Header
  }
};
</script>

<style lang="scss" scoped>
h1 {
  margin: 0;
}
/* .fade-enter-active,
.fade-leave-active {
  transition: all 1s ease;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
  transform: scale(0);
} */

/* 

name-enter -> name-enter-to
name-enter-active

name-leave -> name-leave-to
name-leave-active

*/
</style>
