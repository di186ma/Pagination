<template>
    <div v-if="posts.length > 0">
        <h3>Список языков</h3>
        <post-item
            v-for="post in posts"
            :post="post"
            :key="post.id"
            @remove="$emit('remove', post)"
        />
    </div>
    <h2 v-else style="color: brown;">
        Список пуст
    </h2>

    
</template>

<script>
import PostItem from "@/components/PostItem";
export default {
    components: {
        PostItem
    },
    props: {
        posts: {
            type: Array,
            required: true,
        }
    }
}
</script>

<style scoped>
.post {
  padding: 15px;
  border: 2px solid rosybrown;
  margin-top: 15px;
}
</style>
