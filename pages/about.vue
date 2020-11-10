<template>
<div>
  <v-row>
    <v-card>
        <v-img id="imagenes" :src="src1" max-height="500" width="1500">
          <v-col>
            <h1 class="letraImagen">Reservas naturales de la sociedad civil</h1>
          </v-col>
        </v-img>
    </v-card>
  </v-row>

  <v-row>
    <v-col class="col-xs-12 col-sm-6 col-md-6">
      <CardInformation :configurationImages="{CardWidth:500, ImageHeight: 200, src:'https://babaria.es/wp-content/uploads/2019/09/compromiso.jpg', icon:'mdi-mision', title:'NUESTRO COMPROMISO'}">
          <p>Nuestro compromiso por la Calidad de nuestros productos se basan en cuatro areas: Calidad,
            Seguridad Laboral, Medio Ambiente y Seguridad de Producto. Pensamos que conseguimos repercusiones 
            positivas en nuestros trabajadores y en el entorno ecologico, no olvidando la importancia de elaborar 
            productos seguros para nuestros clientes. Trabajamos para garantizar que los productos cosmeticos 
            fabricados sean adecuados para el uso previsto y para asegurar que no se expone a los consumidores a 
            riesgos a causa de defectos en su seguridad, calidad o eficacia.</p>
        </CardInformation>
    </v-col>

    <v-col class="col-xs-12 col-sm-6 col-md-6">

        <CardInformation :configurationImages="{CardWidth:500, ImageHeight: 200, src:'https://babaria.es/wp-content/uploads/2019/09/cruelty-free.jpg', icon:'mdi-mision', title:'NUESTRA MISIÓN'}">
          <p>Nuestro compromiso por la Calidad de nuestros productos se basan en cuatro areas: Calidad,
            Seguridad Laboral, Medio Ambiente y Seguridad de Producto. Pensamos que conseguimos repercusiones 
            positivas en nuestros trabajadores y en el entorno ecologico, no olvidando la importancia de elaborar 
            productos seguros para nuestros clientes. Trabajamos para garantizar que los productos cosmeticos 
            fabricados sean adecuados para el uso previsto y para asegurar que no se expone a los consumidores a 
            riesgos a causa de defectos en su seguridad, calidad o eficacia.</p>
        </CardInformation>
    </v-col>
  </v-row>

  <v-row>
    <v-col>
      <Parallax :parallaxConfiguration="{height:'600', photo:'https://natureconservancy-h.assetsadobe.com/is/image/content/dam/tnc/nature/en/photos/tnc_17267031.jpg?crop=0,336,5760,3168&wid=2000&hei=1100&scl=2.88'}"></Parallax>
    </v-col>
  </v-row>

    <v-row>

    <v-col class="col-xs-12 col-sm-6 col-md-6">
      <CardInformation :configurationImages="{CardWidth:500, ImageHeight: 200, src:'https://babaria.es/wp-content/uploads/2019/09/compromiso.jpg', icon:'mdi-mision', title:'NUESTRA MISIÓN'}">
          <p>Nuestro compromiso por la Calidad de nuestros productos se basan en cuatro areas: Calidad,
            Seguridad Laboral, Medio Ambiente y Seguridad de Producto. Pensamos que conseguimos repercusiones 
            positivas en nuestros trabajadores y en el entorno ecologico, no olvidando la importancia de elaborar 
            productos seguros para nuestros clientes. Trabajamos para garantizar que los productos cosmeticos 
            fabricados sean adecuados para el uso previsto y para asegurar que no se expone a los consumidores a 
            riesgos a causa de defectos en su seguridad, calidad o eficacia.</p>
        </CardInformation>
    </v-col>

    <v-col class="col-xs-12 col-sm-6 col-md-6">

        <CardInformation :configurationImages="{CardWidth:500, ImageHeight: 200, src:'https://babaria.es/wp-content/uploads/2019/09/cruelty-free.jpg', icon:'mdi-mision', title:'NUESTRA MISIÓN'}">
          <p>Nuestro compromiso por la Calidad de nuestros productos se basan en cuatro areas: Calidad,
            Seguridad Laboral, Medio Ambiente y Seguridad de Producto. Pensamos que conseguimos repercusiones 
            positivas en nuestros trabajadores y en el entorno ecologico, no olvidando la importancia de elaborar 
            productos seguros para nuestros clientes. Trabajamos para garantizar que los productos cosmeticos 
            fabricados sean adecuados para el uso previsto y para asegurar que no se expone a los consumidores a 
            riesgos a causa de defectos en su seguridad, calidad o eficacia.</p>
        </CardInformation>
    </v-col>
  </v-row>
</div>
</template>

<script>
export default {
  data:()=>({
    srcImages:[
    'https://babaria.es/wp-content/uploads/2019/09/header-conocenos.jpg',
    'https://blog.naturlider.com/wp-content/uploads/2020/03/AdobeStock_309195144-post-dia-mundial-naturaleza.jpeg',
    'https://www.virtualpro.co/noticiasImg/52469/20191129-naturaleza.jpg'
    ],
    src1: 'https://babaria.es/wp-content/uploads/2019/09/header-conocenos.jpg',
    contador: 0
  }),
  methods:{
      cambiarImagen:function(){
              setInterval(() => {
                if(this.contador>2){
                  this.contador = 0;
                }
                  this.src1 = this.srcImages[this.contador];
                this.contador = this.contador + 1;
          }, 5000)
      }
  },
  created(){
    this.cambiarImagen();
  },
}
</script>

<style>
#imagenes:before {
	content:'';
	position: absolute;
  top: 0;
	bottom: 0;
	left: 0;
	right: 0;
	background-color: rgba(0,0,0,0.6);
}

.letraImagen {
color: white;
position: absolute;
top: 50%; 
-ms-transform: translateY(-50%);
transform: translateY(50%);
text-align:"center"
}

</style>