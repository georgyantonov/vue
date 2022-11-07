<template>
    <div>
        <my-button @click="showDialog">
            Создать пост
        </my-button>
        <my-dialog v-model:show="dialogVisible">
            <PostForm
                @create="createPost"
                :posts="posts"
            />
        </my-dialog>
        <PostList
            :posts="posts"
            @remove="removePost"
        />
    </div>
</template>

<script>
import PostForm from '@/components/PostForm.vue'
import PostList from '@/components/PostList.vue'
    export default {
        components: {
            PostForm,
            PostList,
        },
        data(){
            return {
                posts: [
                    {id: 1, title: 'JavaScript', body: 'Пост о JS'},
                    {id: 2, title: 'Go', body: 'Пост о Go'},
                    {id: 3, title: 'Ruby', body: 'Пост о Ruby'},
                    {id: 4, title: 'Python', body: 'Пост о Python'},
                ],
                dialogVisible: false,
            }
        },
        methods:{
            addLike(){
                this.likes += 1
            },
            addDislike(){
                this.dislikes += 1
            },
            createPost(post){
                this.dialogVisible = false
                this.posts.push(post)
            },
            removePost(post){
                this.posts = this.posts.filter(p => p.id !== post.id)
            },
            showDialog(){
                this.dialogVisible = true
            }
        
        }
    }
</script>

<style>
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
#app{
    padding: 20px;
}
</style>