<template>
    <div class="instrumento">
        <div :style="{ backgroundImage: `url(${foto})` }" class="avatar"></div>
        <h2>{{ nombre }}</h2>
        <p>{{ precio }}</p>
    </div>
</template>

<script>
export default {
    props: ["foto", "nombre", "precio"],
}
</script>

<style scoped>
.instrumento {
    margin-top: 10px;
    text-align: center;
    width: fit-content;
}

.avatar {
    background-size: cover;
    background-position: center;
    height: 200px;
    width: 200px;
    border-radius: 50%;
}
</style>
