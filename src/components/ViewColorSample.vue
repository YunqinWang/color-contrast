<script >

  export default {
    data: function () {
      return {
        sampleText: 'Sample Text'
      }
    },
    props: {
      sampleTextColor: {
        type: String
      },
      sampleBackColor: {
        type: String
      }
    },

  }
</script>

<template>
  <div class="sample-box"  :style={background:sampleBackColor}>
    <p class="sample-text" :style={color:sampleTextColor}>{{ this.sampleText }}</p>
  </div>
</template>

<style>
  .sample-box{
    position: relative;
  }
  .sample-text{
    font-size: 30px;
    font-weight: 600;
    margin: 0;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }
</style>
