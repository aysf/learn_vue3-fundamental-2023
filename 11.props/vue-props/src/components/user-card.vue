<script>
export default {
    props: {
        user: {
            type: Object,
            required: true
        },
        changeName: {
            type: Function,
            required: true
        }
    },
    emits: ["change-name"],
}
</script>

<template>
    <h1>User</h1>
    <p>User: {{ user.name }}</p>
    <p>Favorite Food: {{ user.food }}</p>
    <button @click="$emit('change-name')">Change Name</button>

</template>