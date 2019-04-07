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
      <label for="tags">Tags</label>
      <select name="tags" id="tags">
        <option value="that_should_be_multiselect"
          >that_should_be_multiselect</option
        >
        <option value="javascript">javascript</option>
        <option value="css">css</option>
        <option value="html">html</option>
      </select>
    </div>
  </div>
</template>
<script>
// @ is an alias to /src
// import TagsCloud from "@/components/TagsCloud.vue";
// import FilteredResults from "@/components/FilteredResults.vue";

export default {
  name: "add",
  data() {
    return {
      title: "lets explore kubernetes",
      url: "https://medium.com/@thisiskj/lets-explore-kubernetes-5477244ef323",
      short_description: "something about kubernetes",
      description: "something about kubernetes",
      tags: ["kubernetes", "javascript"]
    };
  }
  // components: {
  //   TagsCloud,
  //   FilteredResults
  // }
};
</script>
