<template>
<div>
  <v-row>
    <v-col class="col-lg-12 col-sm-12 col-xs-12">
      <v-img max-height="400" src="https://mir-s3-cdn-cf.behance.net/project_modules/2800_opt_1/0c49f2101845141.5f28ca4445ab5.jpg"></v-img>
    </v-col>
    </v-row>
    <v-row>
      <v-card class="col-10 offset-1" height="60" color="grey lighten-2" style="border:solid">
        <h1 style="text-align:center; color:grey"><v-icon>mdi-phone</v-icon> Contacto</h1>
      </v-card>
    </v-row>
  <v-row>
    <v-col cols="12" class="col-sm-10 offset-sm-1 col-md-4 col-lg-4 mt-6">
      <div class="mt-15"><p style="text-align:center">Si necesitas ponerte en contacto con nosotros solo tienes que completar el siguiente formulario y nos pondremos en contacto contigo a la mayor brevedad posible.</p></div>
    </v-col>
    <v-col cols="12" class="col-sm-10 offset-sm-1 col-md-6 col-lg-6 offset-lg-1 mt-6">
      <v-form ref="form" v-model="valid" lazy-validation>
            <v-text-field
            v-model="name"
            :counter="10"
            :rules="nameRules"
            label="Name"
            required
            ></v-text-field>

            <v-text-field
            v-model="email"
            :rules="emailRules"
            label="E-mail"
            required
            ></v-text-field>

            <v-select
            v-model="select"
            :items="items"
            :rules="[v => !!v || 'Item is required']"
            label="Item"
            required
            ></v-select>

            <v-checkbox
            v-model="checkbox"
            :rules="[v => !!v || 'You must agree to continue!']"
            label="Do you agree?"
            required
            ></v-checkbox>

            <v-btn
            :disabled="!valid"
            color="primary"
            class="mr-4 col-lg-6 offset-lg-3"
            @click="GuardarInformacionContacto"
            > Enviar
            </v-btn>
      </v-form>
    </v-col>
  </v-row>
  <br>
  <v-row>
    <v-card class="col-10 offset-1" height="60" color="grey lighten-2" style="border:solid">
      <h1 style="text-align:center; color:grey"><v-icon>mdi-Social</v-icon> Redes sociales</h1>
    </v-card>
  </v-row>
  <br>
  <v-row align="center" justify="center">
    <v-col class="col-xs-12 col-sm-12 col-md-12 col-lg-4">
      <div style="overflow:scroll; height: 500px">
          <h1>Twitter</h1>
          <br>
          <a class="twitter-timeline" href="https://twitter.com/segescot?ref_src=twsrc%5Etfw">Tweets by segescot</a> 
          <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
      </div>
    </v-col>

    <v-col cols="10" class="col-xs-10 offset-xs-1 col-sm-8 offset-sm-2 col-md-8 offset-md-3 col-lg-4">
        <iframe src="https://www.facebook.com/plugins/page.php?href=https%3A%2F%2Fwww.facebook.com%2Fsegescot&tabs=timeline&width=400&height=500&small_header=false&adapt_container_width=true&hide_cover=false&show_facepile=true&appId" width="400" height="500" style="border:none;overflow:hidden" scrolling="no" frameborder="0" allowTransparency="true" allow="encrypted-media"></iframe>
    </v-col>
    
    <v-col style="text-align:center;margin-top:100px">
      <div style="float:center">
        <hr class="style18">
        <h1>Correo electrónico:</h1>
        <br>
        <p>-segescot@gmail.com</p>
        <v-btn color="green" large>
                <v-icon>mdi-whatsapp</v-icon>
                <h3>Contactanos por whatsapp</h3>
        </v-btn>
        <hr class="style18" style="margin-top:30px">
      </div>
    </v-col>
  </v-row>
  </div>
</template>

<script>
  export default {
    data: () => ({
      valid: true,
      name: '',
      nameRules: [
        v => !!v || 'Name is required',
        v => (v && v.length <= 10) || 'Name must be less than 10 characters',
      ],
      email: '',
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /.+@.+\..+/.test(v) || 'E-mail must be valid',
      ],
      select: null,
      items: [
        'Item 1',
        'Item 2',
        'Item 3',
        'Item 4',
      ],
      checkbox: false,
    }),
    methods: {
      validate () {
        this.$refs.form.validate()
      },
      reset () {
        this.$refs.form.reset()
      },
      GuardarInformacionContacto(){
      this.$axios.post('/components/create', {
        }).then(response => {
      })
      }
    },
  }
</script>

<style scoped>
body{
  background-color: #f0f0f0;
  width: 700px;
  float: center;
}

hr.style18 { 
  height: 30px; 
  border-style: solid; 
  border-color: #8c8b8b; 
  border-width: 1px 0 0 0; 
  border-radius: 20px; 
} 
hr.style18:before { 
  display: block; 
  content: ""; 
  height: 30px; 
  margin-top: -31px; 
  border-style: solid; 
  border-color: #8c8b8b; 
  border-width: 0 0 1px 0; 
  border-radius: 20px; 
}

.embed-container {
    position: relative;
    padding-bottom: 56.25%;
    height: 0;
    overflow: hidden;
}
.embed-container iframe {
    position: absolute;
    top:0;
    left: 0;
    width: 100%;
    height: 100%;
}
</style>