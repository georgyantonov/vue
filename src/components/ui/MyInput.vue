<template >
    <input 
        class='input' 
        type="text"
        @input="updateInput"
    >
</template>

<script>
export default {
    name: "MyInput",
    props: {
        modelValue: [String, Number]
    },
    methods: {
        updateInput(e) {
            this.$emit('update:modelValue', e.target.value)
        }
    }
}
</script>
<style>
.input{
    width: 100%;
    border: 2px solid teal;
    padding: 10px 15px;
    margin: 15px 0 15px 0;
}
</style>