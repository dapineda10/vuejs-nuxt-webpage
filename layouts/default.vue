<template>
<v-app>
  <div>
      <!--Menu escritorio-->
        <div class="d-none d-md-block">
          <Footer :configuracion="{absolute: false, colorText: 'black', colorFooter: 'white', showEmail: true}"></Footer>
            <AppBarDesktop :margen="clase"></AppBarDesktop>
        </div>

      
      <!--Menu celular-->
      <div class="d-flex d-md-none">
        <Footer :configuracion="{absolute: true, colorText: 'white', colorFooter: '#34515e', showEmail: false}"></Footer>
        <SideBarMobile></SideBarMobile>
      </div>  
    
      <v-container v-scroll="onScroll" class="contenido" fluid>
        <router-view></router-view>
      </v-container>
  </div>
</v-app>
</template>

<style>
@media (min-width: 960px) {
.contenido {
    margin-top: 60px;
  }
}
</style>

<script>
  export default {
    data:()=>({
      clase : true,
    }),
    props: {
      icon: {
        type: String,
        default: '$cancel'
      }
    },
    created(){
    if (process.client) { 
      if(window.scrollY === 0){
        this.clase = true
      }else{
        this.clase = false
      }
    }
    },
    methods:{
      onScroll(e){
        if(window.pageYOffset === 0){
          this.clase=true;
        }else{
          this.clase=false;
        }
        }
      }
    }
</script>