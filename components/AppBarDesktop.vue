<template>
    <v-app-bar :class="{'mt-12':margen}" color="white" style="transition:0.3s" app>
          <v-row>
              <v-col cols="2">
                  <v-icon large color="pink darken-1">mdi-account</v-icon>
              </v-col>
              <v-col cols="8" class="offset-2">
                  <v-tabs>
                      <v-tab v-for="(item, index) in items" :key="index" :to="item.url">
                        {{item.title}}
                      </v-tab>
                  </v-tabs>
              </v-col>
          </v-row>
        </v-app-bar>
</template>

<style>
</style>

<script>
  export default {
      data:()=>({
      items: [
          { id: 1, title: 'Inicio', icon: 'mdi-home', url: '/'},
          { id: 2, title: 'Conocenos', icon: 'mdi-nature-people' , url:'about'},
          { id: 3, title: 'Contactanos', icon: 'mdi-phone', url:'contact'},
        ],
    }),
    props: ['margen'],
  }
</script>

<style>
</style>