<template>
<v-card class="mx-auto" :max-width="configurationImages.CardWidth">
    <v-img class="white--text align-end" height="200" :src="configurationImages.src"></v-img>
    <div class="mt-8 offset-1"><h4><v-icon>{{configurationImages.icon}}</v-icon><h1>{{configurationImages.title}}</h1></h4></div>
    <v-card-text>
        <div>
            <slot></slot>
        </div>
    </v-card-text>
</v-card>
</template>

<script>
export default {
    props:{
        configurationImages:Object
    }
}
</script>