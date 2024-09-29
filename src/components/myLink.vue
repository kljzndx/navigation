<script setup lang="ts">
const props=defineProps<{
    link:string,
    text:string,
}>();
</script>
<template>
    <div>
        <a class="my-link" :href="props.link">{{ props.text }}</a>
    </div>
</template>
<style scoped>
.my-link{
    display: block;
    width: max-content;
    padding: 0.5rem 0.75rem;
    background-color: hsl(0, 0%, 90%);
    text-decoration: none;
    color: black;
}
.my-link:hover{
    background-color: hsl(0, 0%, 80%);
}
</style>
