<template>
    <div class="header">
        <h2>{{ title }}</h2>
        <p>{{ description }}</p>
    </div>
</template>

<script>
// import TagsCloud from "@/components/TagsCloud.vue";
// import FilteredResults from "@/components/FilteredResults.vue";

export default {
    name: "add",
    props: {
        title: String,
        description: String
    }
    // components: {
    //   TagsCloud,
    //   FilteredResults
    // }
};
</script>
