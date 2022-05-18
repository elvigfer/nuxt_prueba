<template>
    <img class="banner" :src="source" :alt="alt">
</template>

<script>
export default{
    props: ['source', 'alt']
}
</script>

<style lang="postcss">
.banner{
    @apply w-full;
}
</style>