<template>
    <div class="card">
        <img style="height: 100px;" :src="imgSrc" alt="Card Image" class="card-image" />
        <div class="card-content">
            <!-- <h3>Title</h3>
            <p>Description</p>
            <button>Ver más</button> -->
            <slot />
        </div>
    </div>
</template>

<script>
export default {
    props: ["imgSrc"]
}
</script>

<style scoped>

</style>