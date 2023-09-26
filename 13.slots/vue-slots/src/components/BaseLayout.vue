<script>
export default{

}
</script>

<template>
    <div class="wrapper">

        <aside class="aside">
            <slot name="aside"> Aside Default Content </slot>
        </aside>

        <main class="main">
            <slot name="main">Main Default Content</slot>
        </main>

        <footer class="footer">
            <slot name="footer">Footer Default Content</slot>
        </footer>

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