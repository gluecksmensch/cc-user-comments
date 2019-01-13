<template>
  <article class="comment">
    <h3>{{ title }}</h3>
    <p>{{ body }}</p>
  </article>
</template>

<script>
export default {
  name: "Comment",
  props: {
    id: {
      type: Number,
      default: ""
    },
    title: {
      type: String,
      default: ""
    },
    body: {
      type: String,
      default: ""
    }
  }
};
</script>
