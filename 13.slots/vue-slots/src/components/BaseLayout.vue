<script>
export default{

}
</script>

<template>
    <div class="wrapper">

        <div class="aside">
            <slot name="aside"> Aside Default Content </slot>
        </div>

        <div class="main">
            <slot name="main">Main Default Content</slot>
        </div>

        <div class="footer">
            <slot name="footer">Footer Default Content</slot>
        </div>

    </div>
</template>

<style>
.aside {
    border: 2px solid red;
}
.main {
    border: 2px solid yellow;
}
.footer {
    border: 2px solid blue;
}

</style>