<script>
export default{
    props: {
        characterProps: {
            type: Object,
            required: true,
        }
    },
    emits: ["favorite"],
    methods: {
        favoriteCharacter() {
            this.$emit("favorite", this.characterProps)
        }
    }
}
</script>

<template>
    <div>
        <p>{{ characterProps.name }}</p>
        <button @click="favoriteCharacter">⭐ Favorite</button>
    </div>
</template>