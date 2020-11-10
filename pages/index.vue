<template>
<div>
    <v-row>
      <v-col class="col-sm-12 col-md-6">
        <Images :configuration ="{src:'https://estaticos.muyinteresante.es/media/cache/760x570_thumb/uploads/images/article/590c38d75bafe8cb903c9869/tucan_0.jpg', width:'1000', height:'400'}">
          <v-btn @click="mostrar" large color="#1976d2">Ver más</v-btn>
        </Images>
      </v-col>
      <v-col class="d-none d-md-block" cols="6">
        <v-row>
          <v-col cols="10" class="offset-1">

          <v-hover v-slot:default="{ hover }" open-delay="100">
            <div class="CardInformation">
              <v-card tile :elevation="hover ? 20 : 3">
              <v-card-title>
                <div><h1>¿Qué es un tucán?</h1></div>
                <p>
                  <br>
                  Se conoce como tucán, diotedé o diostedé a una familia de aves.
                  <br>
                  Se trata de una familia sumamente amplia, que alberga seis géneros y 
                  cuarenta y dos especies diferentes, todas caracterizadas por picos muy 
                  largos y voluminosos, y de colores vistosos.</p>
              </v-card-title>
              </v-card>
            </div>
          </v-hover>
            </v-col>
          </v-row>
          <v-row class="mt-10 offset-3">
            <v-btn color="green" large>
              <v-icon>mdi-whatsapp</v-icon>
              <h3>Contactanos por whatsapp</h3>
            </v-btn>
          </v-row>
      </v-col>
    </v-row>
    <v-row justify="center">
        <h1>Descubre</h1>
    </v-row>

    <v-row justify="center">
        <p style="text-align:center">Los mejores planes y precios para hacer crecer tu empresa, <br>negocio o producto.</p>
    </v-row>

    <v-row justify="center">
        <v-col cols="12" class="col-sm-4 col-md-4 col-lg-4">
          <Lista :items="{titulo:'Precio 1', items:[{contenido:'toda la descripción del primer precio'},{contenido:'toda la descripción del primer precio'}]}"></Lista>
        </v-col>

        <v-col cols="12" class="col-sm-4 col-md-4 col-lg-4">
          <Lista :items="{titulo:'Precio 2', items:[{contenido:'toda la descripción del segundo precio'},{contenido:'toda la descripción del segundo precio'},{contenido:'toda la descripción del segundo precio'}]}"></Lista>
        </v-col>

        <v-col cols="12" class="col-sm-4 col-md-4 col-lg-4">
          <!--<TextCard :TextCardConfiguration ="{img:'https://www.psicoactiva.com/wp-content/uploads/2015/01/hobbies.jpg', title:'Lo que me gusta', subtitle:'Amo programar', content:'La programación me inspira, me hace ser una mejor persona, amor leer, me gusta estar con mi familia.'}">
            <v-btn color="orange" text> Conocer más... </v-btn>
          </TextCard>-->
          <Lista :items="{titulo:'Precio 3', items:[{contenido:'toda la descripción del tercer precio'},{contenido:'toda la descripción del tercer precio'},{contenido:'toda la descripción del tercer precio'},{contenido:'toda la descripción del tercer precio'}]}"></Lista>
        </v-col>
      </v-row>
  </div>
</template>

<script>
  export default {
    head () { 
    return { 
      title: 'Naturaleza en Colombia', 
      meta: [ 
        { hid: 'descripción', nombre: 'descripción', contenido: 'Acerca de la naturaleza en Colombia'} 
      ] 
    } 
  },
    data () {
      return {
        items: [
          {
            src: 'https://ing-sistemas.com/wp-content/uploads/2020/01/Estaciondetrabajoprogramacion.jpg',
          },
          {
            src: 'https://cdn.computerhoy.com/sites/navi.axelspringer.es/public/styles/480/public/media/image/2020/02/programacion-1865211.jpg?itok=RuFStqRQ',
          },
          {
            src: 'https://indexdesarrollo.com/wp-content/uploads/2017/11/aprender-programacion-web.jpg',
          }
        ],
      }
    },
    methods:{
      mostrar:function(){
        alert("Gracias por dar click");
      }
    }
  }
</script>


<style scoped>
.CardInformation{
  border:#1976d2 10px outset;
}
</style>