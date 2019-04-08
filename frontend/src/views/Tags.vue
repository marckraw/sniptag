<template>
    <div class="tags">
        <div class="tags__item" v-for="tag in tags" :key="tag">{{ tag }}</div>
    </div>
</template>
<script>
import { data } from "../data/hardcodedData";

export default {
    name: "Tags",
    data() {
        return {
            tags: ["javascript", "react", "css"]
        };
    },
    mounted() {
        this.fetchTags();
    },
    methods: {
        getAllTags() {
            const tags = data
                .map(resource => resource.tags)
                .reduce((prevVal, curr) => [...prevVal, ...curr], []);
            const set = new Set(tags);
            const uniqueTags = Array.from(set);

            return uniqueTags;
        },
        fetchTags() {
            const tags = this.getAllTags();
            this.tags = tags;
            console.log("fetching tagss");
        }
    }
};
</script>
<style lang="scss" scoped>
.tags {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-gap: 10px;

    @media (min-width: 600px) and (max-width: 899px) {
        grid-template-columns: repeat(3, 1fr);
    }
    @media (min-width: 900px) {
        grid-template-columns: repeat(6, 1fr);
    }
}

.tags__item {
    padding: 10px;
    border-radius: 10px;
    background-color: #eeeeee;
}
</style>
