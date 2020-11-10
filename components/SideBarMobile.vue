<template>
<div class="col-12 general">
      <v-toolbar color="white">
          <div> 
              <v-app-bar-nav-icon @click.stop="drawer = !drawer" large class="offset-1"></v-app-bar-nav-icon>
          </div>

        <v-toolbar-title>Title</v-toolbar-title>

        <v-spacer></v-spacer>

        <v-btn icon>
          <v-icon>mdi-magnify</v-icon>
        </v-btn>

        <v-btn icon>
          <v-icon>mdi-heart</v-icon>
        </v-btn>

        <v-btn icon>
          <v-icon>mdi-dots-vertical</v-icon>
        </v-btn>
      </v-toolbar>

      <v-navigation-drawer v-model="drawer" absolute temporary color="#8eacbb">
      
        <v-list-item>
          <v-list-item-avatar>
            <v-img src="https://randomuser.me/api/portraits/men/78.jpg"></v-img>
          </v-list-item-avatar>

          <v-list-item-content>
            <v-list-item-title>John Leider</v-list-item-title>
          </v-list-item-content>
        </v-list-item>

        <v-divider></v-divider>

        <v-list dense>
          <v-list-item
            v-for="item in items"
            :key="item.title"
            link
            :to="item.url"
          >
            <v-list-item-icon>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-item-icon>

            <v-list-item-content>
              <v-list-item-title v-text="item.title"></v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </v-navigation-drawer>
</div>
</template>


<script>
export default {
data:()=>({
    drawer: null,
    items: [
          { id: 1, title: 'Inicio', icon: 'mdi-home', url: '/'},
          { id: 2, title: 'Conocenos', icon: 'mdi-nature-people' , url:'about'},
          { id: 3, title: 'Contactanos', icon: 'mdi-phone', url:'contact'},
        ]   
})
}
</script>

<style scoped>
.general{
    padding: 0em;
}
</style>