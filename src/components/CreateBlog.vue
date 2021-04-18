<template>
  <div @click="createBlog">
    create blog
  </div>
</template>

<script>
import { DataStore } from '@aws-amplify/datastore';
import { Blog } from '../models';

export default {
  methods: {
    async createBlog() {
      console.log('cerate')
      await DataStore.save(
        new Blog({
          name: "Lorem ipsum dolor sit amet",
          posts: [],
        })
      );
    },
  },
};
</script>
