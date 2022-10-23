<template>
    <button class="btn">
        <slot></slot>
    </button>
</template>
<script>
export default {
    name: "MyButton"
}
</script>
<style>
.btn{
    align-self: flex-end;
    padding: 10px;
    background: none;
    border: 1px solid teal;
    color: teal;
}
</style>