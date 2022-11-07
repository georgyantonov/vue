<template>
    <div class="post">
        <div class="post__content">
            <div>Пост о <strong>{{ post.title }}</strong></div>
            <div class="post__body">
                <p>{{ post.body }}</p>
            </div>
        </div>
        <div class="post__btns">
            <MyButton
                class="delete__btn"
                @click="$emit('remove', post)"
            >
                Удалить
            </MyButton>
        </div> 
    </div>
</template>

<script>

export default {
    props: {
        post: {
            type: Object,
            required: true
        }
    },
    methods: {
        deletePost(){

        }
    }
}
</script>

<style >
.post{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    gap: 10px;
    padding: 15px;
    border: 2px solid teal;
    margin-top: 15px;
}
.post__content{
    max-height: 100%;
}
.post__btns{
    display: flex;
    flex-direction: row;
    justify-content: center;
    gap: 15px;
}
</style>