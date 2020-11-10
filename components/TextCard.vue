<template>
    <v-card
        class="mx-auto"
        max-width="500"
    >
        <v-img
        class="white--text align-end"
        height="200px"
        :src="TextCardConfiguration.img"
        >
        <v-card-title>{{TextCardConfiguration.title}}</v-card-title>
        </v-img>

        <v-card-subtitle class="pb-0">{{TextCardConfiguration.subtitle}}</v-card-subtitle>

        <v-card-text class="text--primary">
        <div>
            {{TextCardConfiguration.content}}
        </div>
        </v-card-text>

        <v-card-actions>
            <slot></slot>
        </v-card-actions>
    </v-card>
</template>

<script>
  export default {
      props: ['TextCardConfiguration']
  }
</script>