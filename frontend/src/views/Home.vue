<template>
    <div class="home">
        <TagsCloud :data="tags" />
        <FilteredResults />
    </div>
</template>

<script>
import TagsCloud from "@/components/TagsCloud.vue";
import FilteredResults from "@/components/FilteredResults.vue";

import { data } from "../data/hardcodedData";

export default {
    name: "Home",
    data() {
        return {
            data: {},
            tags: [],
            show: false,
            title: "some title",
            description: "asdlsjkdnfkjsadnfglksdjnlfkjndslk"
        };
    },
    mounted() {
        console.log("Home mounted");
        // this.data = this.fetchData();
        // this.tags = this.getAllTags();
    },
    methods: {
        fetchData() {
            const fetchedData = data;
            return fetchedData;
        },
        getAllTags() {
            const tags = data
                .map(resource => resource.tags)
                .reduce((prevVal, curr) => [...prevVal, ...curr], []);
            const set = new Set(tags);
            const uniqueTags = Array.from(set);

            return uniqueTags;
        }
    },
    components: {
        TagsCloud,
        FilteredResults
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
