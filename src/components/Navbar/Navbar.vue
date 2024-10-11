<template>
    <div>
        <header>
            <h1 style="margin-right: 20px;" @click="componenteARenderizar = 'Home' ">Home</h1>
            <h1 @click="componenteARenderizar = 'Contactos' ">Contactos</h1>
        </header>
        <div>
            <component :is="componenteARenderizar"/>
        </div>
    </div>
</template>



<script>
import Home from "./Home.vue"
import Contactos from "./Contactos.vue"

export default {
    name: "Navbar",
    components: {
        Home,
        Contactos
    },
    data() {
        return {
            componenteARenderizar: "Home"
        }
    }
}

</script>

<style scoped>
header {
    background: rgb(27, 27, 27);
    color: white;
    padding: 5px;
    display: flex;
}
</style>