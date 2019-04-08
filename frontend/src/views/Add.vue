<template>
    <div class="add">
        <h1>This is an adding page</h1>
        <div>
            <label for="title">Title</label>
            <input name="title" id="title" type="text" v-model="title" />
        </div>
        <div>
            <label for="url">Url</label>
            <input name="url" id="url" type="text" v-model="url" />
        </div>
        <div>
            <label for="short_description">Short description</label>
            <textarea
                name="short_description"
                id="short_description"
                type="text"
                v-model="short_description"
            />
        </div>
        <div>
            <label for="description">Description</label>
            <textarea
                name="description"
                id="description"
                type="text"
                v-model="description"
            />
        </div>
        <div>
            <label for="tags">Multiselect Tags</label>
            <multiselect
                v-model="formData.tags.value"
                :options="formData.tags.options"
                :multiple="true"
            ></multiselect>
        </div>
        <div>
            <button @click="submit">Add</button>
        </div>
    </div>
</template>
<script>
import Multiselect from "vue-multiselect";

import { data } from "../data/hardcodedData";

export default {
    name: "add",
    data() {
        return {
            title: "lets explore kubernetes",
            url:
                "https://medium.com/@thisiskj/lets-explore-kubernetes-5477244ef323",
            short_description: "something about kubernetes",
            description: "something about kubernetes",
            tags: ["kubernetes", "javascript"],
            formData: {
                tags: {
                    value: null,
                    options: ["javascript", "css", "html"]
                }
            }
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
            this.formData.tags.options = tags;
            console.log("fetching tagss");
        },
        submit() {
            console.log("submitting...");
        }
    },
    components: {
        Multiselect
    }
};
</script>
