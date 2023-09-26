<script>
export default {
    props: {
        isShortButton: Boolean,
    }
}
</script>

<template>
    <br><br>
    <button>
        <slot v-if="isShortButton">Ok</slot>
        <slot v-else>Submit</slot>

    </button>
</template>