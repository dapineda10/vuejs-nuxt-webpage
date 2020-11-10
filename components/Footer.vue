<template>
    <v-footer :color="configuracion.colorFooter" :absolute="configuracion.absolute" class="footer" shaped justify-center>
          <v-icon >mdi-email</v-icon><span v-if="configuracion.showEmail" :style="{'color':configuracion.colorText}">segescot@gmail.com</span>
          <v-spacer></v-spacer>
          <v-icon>mdi-facebook</v-icon>
          <v-divider class="mx-4" vertical></v-divider>
          <v-icon>mdi-whatsapp</v-icon>
          <v-divider class="mx-4" vertical></v-divider>
          <v-icon>mdi-instagram</v-icon>
          <v-divider class="mx-4" vertical></v-divider>
          <v-icon>mdi-twitter</v-icon>
     </v-footer>
</template>

<script>
  export default {
     props: ['configuracion']
    }
</script>

<style>
.footer{
  border: red;
}
</style>

