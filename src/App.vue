<template>
  <div id='app'>
  <div class='lamp' v-on:click='toggle'>
    <div class='shade'>
      <div class='light' v-if='on' v-bind:style='{backgroundColor: color, opacity: brightness}'></div>
    </div>
    <div class='base'></div>
  </div>
  <input type='range' min='0' max='1' step='0.1' v-model='brightness'>
  <input type='text' v-model='color'> type a valid CSS color here!
</div>
</template>

<script>
export default {
  name: 'app',
  data(){
    return {
      on: false,
      color: 'purple',
      brightness: 1,
    }
  },
  methods: {
    toggle() {
      this.on = !this.on
    }
  }
}
</script>

<style>
.lamp {
  position: absolute;
  top: 50px;
  left: 50px;
}

.shade {
  position: absolute;
  width: 70px;
  height: 50px;
  background-color: bisque;
}

.light {
  position: absolute;
  width: 100%;
  height: 100%;
  background-color: yellow;
}

.base {
  position: absolute;
  width: 10px;
  height: 70px;
  left: 30px;
  top: 50px;
  background-color: brown;
}
</style>
