<template>
  <div class="container row main-nav">
    <div class="col nav-item no-border" v-on:click="setSelection(0)">
       <img :src="tools[0].icon"></img>
    </div>
    <div class="col nav-item" v-on:click="setSelection(1)">
      <img :src="tools[1].icon"></img>
    </div>
    <div class="col nav-item" v-on:click="setSelection(2)">
      {{tools[2].name}}
    </div>
    <div class="col nav-item" v-on:click="setSelection(3)">
      <!-- {{tools[3].name}} -->
      <img :src="tools[3].icon" width="18px" height="18px"></img>
    </div>
  </div>
</template>


<script>
  export default {
    name: 'Navigation',
    props: ['setSelection', 'tools']
  }
</script>

<style>
/* Styles */
.main-nav {
  background: #6A8EAE; 
  color: white;
  min-height: 2.25em;
  margin: 0;
  padding: .25em 1em;
  text-align: center;
}

.nav-item {
  border-left: 1px solid white;
}
.nav-item:hover {
  cursor:pointer
}
.nav-text:hover {
  cursor:pointer
}
.nav-text {
  pointer-events: none !important; 
}
.no-border {
  border: 0;
}
</style>
