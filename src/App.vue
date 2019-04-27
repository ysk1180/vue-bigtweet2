<template>
  <div>
    <div>
      <input type="radio" id="black" value="black" v-model="image">
      <label for="black"><img src="./assets/black.png"></label>
      <input type="radio" id="red" value="red" v-model="image">
      <label for="red"><img src="./assets/red.png"></label>
    </div>
    <div>
      <b-form-textarea v-model="msg" placeholder="ここに入力してください" rows="2"></b-form-textarea>
    </div>
    <div id="preview">
      <img :src="image_path(image)" />
      <p>{{ msg }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      msg: '',
      image: 'black'
    }
  },
  methods: {
    image_path: function(value) {
      return require("./assets/" + value + ".png")
    }
  }
}
</script>

<style>
#preview {
  width: 315px;
  text-align: center;
  display: inline-block;
  margin-bottom: 20px;
  position: relative;
}
#preview p {
  position: absolute;
  top: 50%;
  left: 50%;
  -ms-transform: translate(-50%,-50%);
  -webkit-transform: translate(-50%,-50%);
  transform: translate(-50%,-50%);
  margin:0;
  padding:0;
  font-size: 35px;
  color: white;
  white-space: pre;
  line-height: 1em;
  text-align: initial;
  font-weight: bold;
}
</style>
