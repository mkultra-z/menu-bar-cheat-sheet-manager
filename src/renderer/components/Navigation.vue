<template>
  <div id="wrapper" class="container row main-nav">
    <div class="col nav-item no-border" v-on:click="reverseMessage(tools[0].name)">
      {{tools[0].name}}
    </div>
    <div class="col nav-item">
      {{tools[1].name}}
    </div>
    <div class="col nav-item">
      {{tools[2].name}}
    </div>
    <div class="col nav-item">
      ...
    </div>
  </div>
</template>


<script>
  export default {
    name: 'Navigation',
    methods: {
      open (link) {
        this.$electron.shell.openExternal(link)
      },
      reverseMessage: function (message) {
        message = message.split('').reverse().join('')
      }
    },
    data () {
      return {
        tools: [{ name: 'Git' }, { name: 'Yarn' }, { name: 'Docker' }]
      }
    }
  }
</script>

<style>
/* Styles */
.main-nav {
  background: #212121;
  color: white;
  min-height: 2.25em;
  margin: 0;
  padding: .25em 1em;
  text-align: center;
}

.nav-item {
  border-left: 1px solid #424242;
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
