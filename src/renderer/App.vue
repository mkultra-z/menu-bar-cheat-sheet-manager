<template>
  <div id="app">
    <navigation></navigation>
    <command v-for="(command, index) in commands" 
      v-bind:command="command" 
      v-bind:index="index"></command>
  </div>
</template>

<script>
  import Navigation from '@/components/Navigation'
  import Command from '@/components/Templates/Command'
  import 'bootstrap/dist/css/bootstrap.css'
  import 'bootstrap-vue/dist/bootstrap-vue.css'

  export default {
    name: 'menu-bar-cheat-sheet-manager',
    components: {
      Navigation,
      Command
    },
    data () {
      return {
        commands: [
          {
            command: 'git clone <remote> -b <branch>',
            description: 'Clone a remote branch'
          },
          {
            command: 'git pull <remote> -b <branch>',
            description: 'Pull the latest code from a remote branch'
          },
          {
            command: 'git commit -a -m "commit message"',
            description: 'Creates a commit with all the staged files'
          }
        ]
      }
    }
  }
</script>

<style>
/* CSS */
/* .html {
  max-width: 325;
  max-height: 400;
  overflow: hidden;
  white-space: none;
} */
body {
  background: #323232;
}
.container {
margin: 0;
padding: 0;
}
</style>
