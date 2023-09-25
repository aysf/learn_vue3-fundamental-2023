<script>
export default {
    props: {
        user: {
            type: Object,
            required: true
        }
    }
}
</script>

<template>
    <h1>User</h1>
    <p>User: {{ user.name }}</p>
    <p>Favorite Food: {{ user.food }}</p>

</template>