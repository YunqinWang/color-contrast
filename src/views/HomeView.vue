<script setup>
  import InputColor from '@/components/InputColor.vue'
  import ViewColorSample from '@/components/ViewColorSample.vue'
  import ColorScore from '@/components/ColorScore.vue'
</script>

<script>
  export default {
    components: {
      InputColor,
      ViewColorSample
    },
    data: function () {
      return {
          textColor:"#000",
          backColor:"#fff"
      }
    },
    methods: {
      updateTextColor(e){
        this.textColor = e;
      },
      updateBackColor(e){
          this.backColor = e;
      },
    }
  }
</script>

<template>
  <div class="view" >
    <ColorScore class="color-score" :scoreTextColor = "this.textColor" :scoreBackColor = "this.backColor"/>
    <ViewColorSample class = "color-sample"
                  :sampleTextColor = "this.textColor" :sampleBackColor = "this.backColor"/>

    <div class = "color-layout" align="center">
      <InputColor  class = "color-single"
                  @update-color="updateTextColor" inputLabel="Pick text color" typeColor="text"/>
      <InputColor  class = "color-single"
                  @update-color="updateBackColor" inputLabel="Pick background color" typeColor="back"/>
    </div>

  </div>
</template>

<style>
  .view{
      margin-bottom: 1em;
      width:100%;
      padding:0;
  }
  .view div{
    width:100%;
  }
  .color-sample{
    height:300px;
    border-radius: 10px;
    box-shadow: 0 0 10px #dbdbdb;
    margin-bottom: 20px;
  }
  .color-layout{
    display: flex;
    flex-direction: col;
  }
  .color-single:first-child{
    margin-right:10px;
  }
  .color-single:last-child{
    margin-left:10px;
  }
  .color-single,
  .color-score{
    margin-bottom: 20px;
    box-shadow: 0 0 5px #dbdbdb;
    border-radius: 5px;
    padding: 10px 20px;
  }
  .color-single{
    width:50%;
  }

  @media screen and (max-width:1200px) {
    #app{
      width:100%;
    }
  }

  @media screen and (max-width:800px) {

    .color-layout{
      display: block;
    }
    .color-single:first-child{
    margin-right:0px;
    }
    .color-single:last-child{
      margin-left:0px;
    }
    .color-single{
    width:100%;
    }
  }
</style>
