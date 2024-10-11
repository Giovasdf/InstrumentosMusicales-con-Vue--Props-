<template>
  <div>
    <Navbar/>

    <Header />
    <div class="instrumentos">
      <div v-for="(instrumento, indice) in instrumentos">
        <Instrumentos :foto="instrumento.foto" :nombre="instrumento.nombre" :precio="instrumento.precio"
          @eliminarInstrumento="instrumentos.splice(indice, 1)">

          <button>Comprar</button>
        </Instrumentos>

      </div>
    </div>
    <Card :imgSrc="'http://cartodb.github.io/labs_vuejs_intro/src/common/vue_banner.jpg'">
      <h3>Title</h3>
      <p>Description</p>
      <button>Ver más</button>
    </Card>


    <div>
      <p>----------------------</p>
      <h3>Componentes Dinamicos</h3>
      <button @click="componenteARenderizar = 'Letras' ">Letras</button>
      <button @click="componenteARenderizar = 'Numeros' ">Numeros</button>
      <div>
        <component :is="componenteARenderizar"/>
      </div>
    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Instrumentos from './components/Instrumentos.vue'
import Card from './components/Card.vue'
import Letras from './components/Letras.vue'
import Numeros from './components/Numeros.vue'
import Navbar from './components/Navbar/Navbar.vue'
export default {
  components: {
    Header,
    Instrumentos,
    Card,
    Letras,
    Numeros,
    Navbar
  },
  data() {
    return {
      instrumentos: [
        {
          foto: "https://cdnx.jumpseller.com/lucy-rock/image/43497740/resize/800/1000?1702409652",
          nombre: "Bateria",
          precio: "$150.000",
        },
        {
          foto: "https://www.importone.cl/wp-content/uploads/2024/02/208867-1.webp",
          nombre: "Ibanez JEM",
          precio: "$650.000",
        },
        {
          foto: "https://www.ebest.cl/media/catalog/product/cache/47abc4af9d81a631bd44d97ba9797770/6/1/610_3.png",
          nombre: "Teclado Casio",
          precio: "$210.000",
        },
      ],
      componenteARenderizar: "Letras",
    }
  },
}
</script>

<style scoped>
.instrumentos {
  width: 80%;
  margin: 30px auto;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}
</style>
