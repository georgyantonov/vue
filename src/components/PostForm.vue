<template>
    <form @submit.prevent>
        <h2>Создание поста</h2>
        <MyInput 
            v-model="post.title"
            type="text" 
            placeholder="Название"
        />
        <MyInput 
            v-model="post.body"
            type="text" 
            placeholder="Текст поста"
        />
        <MyButton
            @click="createPost" 
            class="create__post"
        >
            Создать
        </MyButton>
    </form>
</template>

<script>
export default {
    data() {
        return {
            post: {
                title: "",
                body: "",
            }
        };
    },
    props: {
        posts:{
            type: Array
        }
    },
    methods: {
        createPost() {
            this.post.id = this.posts[this.posts.length - 1].id + 1;
            this.$emit("create", this.post);
            this.post = {
                title: "",
                body: ""
            };
            this.title = "";
            this.body = "";
        }
    },
}
</script>

<style>
form{
    display: flex;
    flex-direction: column;
}
</style>