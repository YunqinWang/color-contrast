<script setup>
  defineProps({
    inputLabel: {
      type: String,
      required: true,
    },
    typeColor:{
      type: String,
      required: true,
    }
  })

</script>

<script>
export default {
  data: function () {
    return {
      inputColor: this.typeColor=="back" ? "#ffffff": "#000000"
    }
  },
  methods: {
    setColor() {
      this.$emit('update-color', this.inputColor);
    }
  },
}
</script>

<template>
  <div class="colorInputBox">
    <div class="colorInputLeft">
      <p class="colorInputLabel">{{inputLabel}}: </p>
      <p :style="{color:inputColor}">{{inputColor}}</p>
    </div>
    <input v-model = "inputColor" type="color" @change="setColor()"/>
  </div>
</template>

<style>
p{
  font-size: 20px;
  line-height: 140%;
}
input{
  width:20%;
  height:40px;
  padding:0px;
  border:none;
  background: none;
  border-radius: 50%;
}
.colorInputBox{
  display: flex;
  flex-direction: row;
}
.colorInputLeft{
  width: 80%;
  margin-right: 20px;
}

@media screen and (max-width:1200px) {
  .colorInputBox{
  display: block;
  }
  .colorInputLeft{
    width: 100%;
    margin-right: 0px;
  }
  .colorInputLabel{
    float: none;
  }
  input{
  width:60%;
}
}
</style>
