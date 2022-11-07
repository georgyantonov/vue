<template >
    <div v-if="posts.length != 0">
        <h2>Список постов</h2>
        <post 
            v-for="post in posts"
            :post="post"
            :key="post.id"
            @remove="$emit('remove', post)"
        />
    </div>
    <div v-else>
        <h2>Посты не найдены</h2>
        <p>Напишите пост =)</p>
    </div>
    
</template>

<script>
import post from '@/components/Post.vue'
export default {
    components: {
        post
    },
    props:{
        posts: {
            type: Array,
            required: true
        }
    }
}
</script>

<style scoped>

</style>