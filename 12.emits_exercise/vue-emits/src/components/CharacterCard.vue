<script>
export default{
    props: {
        characterProps: {
            type: Object,
            required: true,
        }
    },
    emits: ["favorite"],
}
</script>

<template>
    <div>
        <p>{{ characterProps.name }}</p>
        <button @click="$emit('favorite')">⭐ Favorite</button>
    </div>
</template>