<template>
  <svg class="g-icon">
    <use :xlink:href="`#i-${iconName}`"></use>
  </svg>
</template>

<script>
    export default {
        name: 'g-icon',
        data(){
            return {}
        },
      props:{
        iconName:{}
      }
    }
</script>

<style lang="scss">
  .g-icon {
    width: 1em;
    height: 1em;
    /*更改icon颜色*/
    /*fill:blue;*/
  }
</style>
