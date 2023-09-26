<script>
export default {
    props: {
        userProps: {
            type: Object,
            required: true
        }
    }
}
</script>

<template>
  <p>user_name: {{ userProps.name }}</p>
  <p>food: {{ userProps.food }}</p>
</template>
