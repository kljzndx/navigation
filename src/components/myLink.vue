<script setup lang="ts">
import { computed } from 'vue';

const props=defineProps<{
    link:string,
    text:string,
    info?:string,
}>();

const title=computed(()=>{
    if (props.info)
        return props.text + ': ' + props.info;
    else return undefined;
})
</script>
<template>
    <div>
        <a class="my-link" :title="title" :href="props.link">{{ props.text }}</a>
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
