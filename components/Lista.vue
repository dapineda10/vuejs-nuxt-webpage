<template>
<v-hover v-slot:default="{ hover }" open-delay="100">
    <v-card class="mx-auto" tile :elevation="hover ? 16 : 2">
        <div class="header">
            <h1 style="text-align:center">{{items.titulo}}</h1>
        </div>
        <div v-for="(item,index) in items.items" :key="index">
            <v-divider></v-divider>
            <v-list-item>
                <v-list-item-content>
                <v-list-item-title>
                    <p>Single-line item</p>
                </v-list-item-title>
                <h3>
                    {{item.contenido}}
                </h3>
                </v-list-item-content>
            </v-list-item>
            <v-divider></v-divider>
        </div>
    </v-card>
    </v-hover>
</template>

<script>
export default {
    props:['items']
}
</script>

<style scoped>
.header {
  padding: 10px;
  text-align: center;
  background: #1976d2;
  color: white;
  font-size: 15px;
}
</style>