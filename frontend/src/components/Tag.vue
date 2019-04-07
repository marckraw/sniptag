<template>
  <label>
    <!-- Input element for the checkbox -->
    <input type="checkbox" class="tag-default" />

    <!-- Customization element for the checkbox -->
    <span class="tag-toggle">
      {{ data.name }}
      <span class="tag-toggle__circle"></span>
    </span>
  </label>
</template>

<script>
export default {
  name: "tag",
  props: {
    data: {
      type: Object,
      required: true
    }
  }
};
</script>
