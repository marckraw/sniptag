<template>
    <div class="tags-cloud">
        <Tag v-for="tag in tags" :key="tag" :data="tag" />
    </div>
</template>

<script>
import Tag from "./Tag";

export default {
    name: "tags-cloud",
    data() {
        return {
            tags: ["javascript", "css", "html"]
        };
    },
    props: {
        data: Array
    },
    mounted() {
        console.log("TagsCloud mounted");
        console.log(this.data);
        // this.tags = this.data;
    },
    updated() {
        this.tags = this.data;
    },
    components: {
        Tag
    }
};
</script>

<style></style>
