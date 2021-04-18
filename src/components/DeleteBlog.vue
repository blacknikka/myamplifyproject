<template>
  <div @click="deleteBlog">
    delete blog
  </div>
</template>

<script>
import { DataStore } from '@aws-amplify/datastore';
import { Blog } from '../models';

export default {
  methods: {
   async deleteBlog() {
        const modelToDelete = await DataStore.query(Blog, 123456789);
        DataStore.delete(modelToDelete);
   }
  },
};
</script>
