<template>
  <div @click="queryBlog">
    query blog
  </div>
</template>

<script>
import { DataStore } from "@aws-amplify/datastore";
import { Blog } from "../models";

export default {
  methods: {
    async queryBlog() {
      const models = await DataStore.query(Blog);
      console.log(models);
    },
  },
};
</script>
