<template>
  <button class="g-button" :class="{ [`icon-${iconPosition}`] : true}" @click="$emit('click')">
    <g-icon class="icon" v-if="icons && !loading" :icon-name="icons"></g-icon>
    <g-icon class=" icon loading" v-if="loading" icon-name="loading"></g-icon>
    <div class="slot-content">
      <slot></slot>
    </div>
  </button>
</template>

<script>

  import gicon from '../../icon/icon.vue'

  export default {
    name: 'gl-btn',
    data(){
      return {}
    },
//    props: ['icons', 'iconPosition']
    props: {
      icons: {},
      loading:{
        type: Boolean,
        default: false
      },
      iconPosition: {
          type: String,
        default: 'left',
        validator(val){
            return !(val !== 'left' && val !== 'right');
        }
      }
    },
    components:{
        'g-icon':gicon
    }
  }
</script>

<style lang="scss">

  @keyframes spin {
    0% { transform: rotate(0deg); }
    100% { transform: rotate(360deg); }
  }

  .g-button {
    display: inline-flex;
    font-size: 14px;
    height: 32px;
    padding: 0 1em;
    font: inherit;
    border-radius: 4px;
    border: 1px solid #999;
    background: white;
    cursor: pointer;
    justify-content: center;
    /*子元素在父元素垂直居中*/
    align-items: center;
    /*防止多个button水平放置时会上下参差不齐*/
    vertical-align: middle;

    &:hover {
      border-color: #666;
    }
    &:active {
      background-color: #eee;
    }
    &:focus {
      outline: none;
    }

    > .slot-content {
      order: 2;
    }
    > .icon {
      order: 1;
      margin-right: .3em;
    }

    &.icon-right {
      > .slot-content {
        order: 1;
      }
      > .icon {
        order: 2;
        margin-right: 0;
        margin-left: .3em
      }
    }

  }

  .loading{
    animation: spin 1s infinite linear;
  }

</style>











