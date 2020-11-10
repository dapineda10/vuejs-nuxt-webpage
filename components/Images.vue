<template>
    <div class="contenedor">
        <v-img :src="configuration.src" class="image" :max-width="configuration.width" :max-height="configuration.height">
        </v-img>
        <div class="overlay">
            <div class="text">
                <slot></slot>
        </div>
        </div>
    </div>
</template>

<script>
export default {
    props:
    {
      configuration:Object
    },
}
</script>

<style>
@media (min-width: 960px) {
  .contenedor {
    position: relative;
  }

  .image {
    display: block;
    width: 100%;
    height: auto;
  }

  .overlay {
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    height: 0%;
    width: 0%;
    opacity: 0;
    transition: .5s ease;
    background-image: url("https://concepto.de/wp-content/uploads/2018/08/selva-e1535405554134.jpg");
  }

  .contenedor:hover .overlay {
    opacity: 1;
    height: 100%;
    width: 100%;
  }

  .text {
    color: white;
    font-size: 20px;
    position: absolute;
    top: 90%;
    left: 90%;
    -webkit-transform: translate(-50%, -50%);
    -ms-transform: translate(-50%, -50%);
    transform: translate(-50%, -50%);
    text-align: center;
  }
  }

@media (max-width: 960px) {
  .contenedor {
    position: relative;
  }

  .image {
    display: block;
    width: 100%;
    height: auto;
  }

  .overlay {
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    height: 100%;
    width: 100%;
    opacity: 1;
    transition: .5s ease;
  }

  .text {
    position: absolute;
    bottom: 8px;
    right: 16px;
    font-size: 18px;
  }
  }
</style>