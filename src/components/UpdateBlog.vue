<template>
  <div @click="updateBlog">
    update blog
  </div>
</template>

<script>
import { DataStore } from '@aws-amplify/datastore';
import { Blog } from '../models';

export default {
  methods: {
     async updateBlog() {
/* Models in DataStore are immutable. To update a record you must use the copyOf function
 to apply updates to the item’s fields rather than mutating the instance directly */
        const modelToUpdate = await DataStore.query(Blog, 123456789);
        await DataStore.save(Blog.copyOf(modelToUpdate, item => {
            // Update the values on {item} variable to update DataStore entry
            console(item);
        }));
     }
  },
};
</script>
