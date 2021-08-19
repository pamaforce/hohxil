<template>
  <web-view :src="link"></web-view>
</template>

<script>
export default {
  data() {
    return {
      link: "",
    };
  },
  onLoad(query) {
    this.link = query.link;
  },
  methods: {},
};
</script>