<template>
  <div id="app">
    <navigation v-bind:setSelection="setSelection" v-bind:tools="tools"></navigation>
    <command v-for="(command, index) in tools[selection].commands" 
      :command="command" 
      :index="index"></command>
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
    methods: {
      setSelection (index) {
        this.selection = index
      }
    },
    data () {
      return dataPlease()
    }
  }

  const dataPlease = () => {
    return {
      selection: '0',
      tools: [
        {
          name: 'Git',
          icon: 'data:image/svg+xml;utf8;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iaXNvLTg4NTktMSI/Pgo8IS0tIEdlbmVyYXRvcjogQWRvYmUgSWxsdXN0cmF0b3IgMTYuMC4wLCBTVkcgRXhwb3J0IFBsdWctSW4gLiBTVkcgVmVyc2lvbjogNi4wMCBCdWlsZCAwKSAgLS0+CjwhRE9DVFlQRSBzdmcgUFVCTElDICItLy9XM0MvL0RURCBTVkcgMS4xLy9FTiIgImh0dHA6Ly93d3cudzMub3JnL0dyYXBoaWNzL1NWRy8xLjEvRFREL3N2ZzExLmR0ZCI+CjxzdmcgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB4bWxuczp4bGluaz0iaHR0cDovL3d3dy53My5vcmcvMTk5OS94bGluayIgdmVyc2lvbj0iMS4xIiBpZD0iQ2FwYV8xIiB4PSIwcHgiIHk9IjBweCIgd2lkdGg9IjE2cHgiIGhlaWdodD0iMTZweCIgdmlld0JveD0iMCAwIDMxLjQ1NyAzMS40NTciIHN0eWxlPSJlbmFibGUtYmFja2dyb3VuZDpuZXcgMCAwIDMxLjQ1NyAzMS40NTc7IiB4bWw6c3BhY2U9InByZXNlcnZlIj4KPGc+Cgk8Zz4KCQk8cGF0aCBkPSJNMTcuMTk5LDBjLTAuNjY0LDAtMS4yMzMsMC4yNTItMS43MDUsMC43NTdDMTUuMDI0LDEuMjYxLDE0Ljc5LDEuODcsMTQuNzksMi41ODFjMCwwLjY4OCwwLjIzNiwxLjI4NSwwLjcwNSwxLjc5ICAgIGMwLjQ3MSwwLjUwNCwxLjAzOSwwLjc1NywxLjcwNSwwLjc1N2MwLjY0MiwwLDEuMTk5LTAuMjUyLDEuNjctMC43NTdjMC40Ny0wLjUwNSwwLjcwNS0xLjEwMiwwLjcwNS0xLjc5ICAgIGMwLTAuNzExLTAuMjM1LTEuMzE5LTAuNzA1LTEuODI0QzE4LjM5OCwwLjI1MiwxNy44NDEsMCwxNy4xOTksMHoiIGZpbGw9IiNGRkZGRkYiLz4KCQk8cGF0aCBkPSJNMjcuMzIyLDE5Ljc5Yy0xLjAxLDAtMS41MDgtMC43NjktMS41MDgtMi4zMDZ2LTYuMDdoMy4xNzZWNy42MTlIMjUuODFjLTAuMDEyLTAuNS0wLjA0LTEuNjUxLTAuMDYtMi4xOTFoLTMuNzA5djIuMTkxICAgIGgtMi4wNDl2My43OTRoMi4wNDl2NS44OTdjMCwxLjkyOCwwLjI0MiwzLjM0LDAuNzI3LDQuMjMzYzAuNjQzLDEuMTk0LDEuNzcsMS43OSwzLjQ0MywxLjc5YzEuMTkzLDAsMi4yNDQtMC4yMjksMy4wMzEtMC42ODggICAgdi0zLjQ0MUMyOC42MTUsMTkuNTk2LDI4LjAzMywxOS43OSwyNy4zMjIsMTkuNzl6IiBmaWxsPSIjRkZGRkZGIi8+CgkJPHBhdGggZD0iTTE1LjAwNSw3LjY3NGMtMS4zNDgsMC41MjYtMi42MDMsMC43OTMtMy42ODEsMC43OTNjLTAuOTYyLTAuNTUxLTEuOTYtMC44MjYtMy4wODQtMC44MjYgICAgYy0xLjU2MSwwLTIuOTAxLDAuNTE2LTQuMDI2LDEuNTQ4Yy0xLjE3LDEuMTAyLTEuNzU3LDIuNDc5LTEuNzU3LDQuMTNjMCwxLjEwMiwwLjMxOCwyLjEzMywwLjk2MywzLjA5NyAgICBjMC41NzMsMC44OTUsMS4xNzMsMS40NjksMS45NTgsMS43MjF2MC4wNjljLTAuNzg1LDAuMzIxLTEuMTM0LDEuMTI0LTEuMTM0LDIuNDFjMCwwLjk4NywwLjM0OSwxLjcyMSwxLjEzNCwyLjIwMnYwLjA3ICAgIGMtMi4xNywwLjcwOS0zLjE2MywyLjAyOS0zLjE2MywzLjk1N2MwLDEuNjc2LDAuNzI5LDIuOTAyLDIuMTUzLDMuNjgyYzEuMTIzLDAuNjE5LDIuNTY3LDAuOTMsNC4zMTEsMC45MyAgICBjNC4yNDQsMCw2LjM3MS0xLjc3Nyw2LjM3MS01LjMzNWMwLTIuMjI2LTEuNjM4LTMuNTkxLTQuOTE5LTQuMDk3Yy0wLjc1OS0wLjExNC0xLjMyOS0wLjM4OS0xLjcyLTAuODI1ICAgIGMtMC4yOTktMC4zLTAuNDQ1LTAuNTk3LTAuNDQ1LTAuODk2YzAtMC44NSwwLjQ1OC0xLjM0MywxLjM3Ny0xLjQ3OWMxLjM5OC0wLjIwNywyLjUzOS0wLjg1NCwzLjQyNS0xLjk0NCAgICBjMC44ODItMS4wOSwxLjMyNC0yLjM3LDEuMzI0LTMuODM4YzAtMC40NTgtMC4xMzktMC45NTItMC4zMjEtMS40NzljMC41NDEtMC4xMjYsMC45MzEtMC4yNCwxLjIzNC0wLjM0N3YxMi4xMDJoNC4xNTVWNi45NTMgICAgaC00LjE1NVY3LjY3NHogTTguNjE5LDI0LjgxNGMxLjkyOCwwLDIuODkxLDAuNTg2LDIuODkxLDEuNzU0YzAsMS4yNC0wLjg4MywxLjg1OS0yLjY1LDEuODU5Yy0yLjAxOSwwLTMuMDI3LTAuNTk3LTMuMDI3LTEuNzg5ICAgIEM1LjgzMSwyNS40MjMsNi43NjEsMjQuODE0LDguNjE5LDI0LjgxNHogTTguMzc4LDE1LjcyOWMtMS40NDUsMC0yLjE2OC0wLjc5Mi0yLjE2OC0yLjM3NWMwLTEuNjk4LDAuNzIzLTIuNTQ3LDIuMTY4LTIuNTQ3ICAgIGMwLjY4OSwwLDEuMjI5LDAuMjY0LDEuNjE3LDAuNzkyYzAuMzIxLDAuNDgxLDAuNDgxLDEuMDU1LDAuNDgxLDEuNzIxQzEwLjQ3NywxNC45MjYsOS43NzgsMTUuNzI5LDguMzc4LDE1LjcyOXoiIGZpbGw9IiNGRkZGRkYiLz4KCTwvZz4KPC9nPgo8Zz4KPC9nPgo8Zz4KPC9nPgo8Zz4KPC9nPgo8Zz4KPC9nPgo8Zz4KPC9nPgo8Zz4KPC9nPgo8Zz4KPC9nPgo8Zz4KPC9nPgo8Zz4KPC9nPgo8Zz4KPC9nPgo8Zz4KPC9nPgo8Zz4KPC9nPgo8Zz4KPC9nPgo8Zz4KPC9nPgo8Zz4KPC9nPgo8L3N2Zz4K',
          commands: [
            {
              command: 'git init [project-name]',
              description: 'Creates a new local repository with the specified name'
            },
            {
              command: 'git clone [url] -b [branch] [dir]',
              description: 'Clone a remote repository'
            },
            {
              command: 'git status',
              description: 'Lists all new or modified files to be commited'
            },
            {
              command: 'git diff (opitional) --staged',
              description: 'Shows file differences not yet staged, or between staging and the last file version'
            },
            {
              command: 'git add [file]',
              description: 'Snapshots the file in preparation for versioning'
            },
            {
              command: 'git reset [file]',
              description: 'Unstages the file, but preserve its contents'
            },
            {
              command: 'git commit -m "commit message"',
              description: 'Records file snapshots permanently in version history'
            },
            {
              command: 'git pull <remote> -b <branch>',
              description: 'Pull the latest code from a remote branch'
            },
            {
              command: 'git config --global user.name "[name]"',
              description: 'Sets the name you want atached to your commit transactions'
            },
            {
              command: 'git config --global user.email "[email address]"',
              description: 'Sets the email you want atached to your commit transactions'
            },
            {
              command: 'git config --global color.ui auto',
              description: 'Enables helpful colorization of command line output'
            }
          ]
        },
        {
          name: 'Yarn',
          icon: 'data:image/svg+xml;utf8;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iaXNvLTg4NTktMSI/Pgo8IS0tIEdlbmVyYXRvcjogQWRvYmUgSWxsdXN0cmF0b3IgMTguMS4xLCBTVkcgRXhwb3J0IFBsdWctSW4gLiBTVkcgVmVyc2lvbjogNi4wMCBCdWlsZCAwKSAgLS0+CjxzdmcgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB4bWxuczp4bGluaz0iaHR0cDovL3d3dy53My5vcmcvMTk5OS94bGluayIgdmVyc2lvbj0iMS4xIiBpZD0iQ2FwYV8xIiB4PSIwcHgiIHk9IjBweCIgdmlld0JveD0iMCAwIDU1LjE5MyA1NS4xOTMiIHN0eWxlPSJlbmFibGUtYmFja2dyb3VuZDpuZXcgMCAwIDU1LjE5MyA1NS4xOTM7IiB4bWw6c3BhY2U9InByZXNlcnZlIiB3aWR0aD0iMTZweCIgaGVpZ2h0PSIxNnB4Ij4KPGc+Cgk8cGF0aCBkPSJNNTIuNTksMC4wMTZjLTAuMDkxLDAuMDE1LTguNzc1LDEuNzc3LTYuODU3LDEzLjQ0MWMwLjY5Nyw0LjI1LDAuMzMzLDcuNDQ3LTAuMzI3LDkuNzM4ICAgYy0wLjE1MywwLjUyOS0wLjQ3NCwwLjUzMy0wLjcsMC4wMzFDNDEuMTQ1LDE1LjM3MiwzMy4yMzksOS44OTQsMjQuMDcsOS44OTRjLTEyLjQ4OCwwLTIyLjY0OSwxMC4xNi0yMi42NDksMjIuNjQ3ICAgYzAsNS41MzcsMiwxMC42MTEsNS4zMTEsMTQuNTUxYzMuMzU5LDMuOTg4LDguMDQ3LDYuOCwxMy4zNzEsNy43NDRjMC41NDMsMC4wOTcsMC45OTksMC4xNjYsMS4wMTQsMC4xODMgICBjMC4wMTQsMC4wMTQsMC4wMzUsMC4wMTksMC4wNDgsMC4wMDZjMC4wMTMtMC4wMTUsMC40NjcsMC4wMzcsMS4wMTcsMC4wODRjMC42MjMsMC4wNTYsMS4yNTMsMC4wODQsMS44OSwwLjA4NCAgIGMxMi40ODksMCwyMi42NDktMTAuMTYyLDIyLjY0OS0yMi42NDljMC0xLjU2Ni0wLjE2Mi0zLjA5NS0wLjQ2Ny00LjU3MmMtMC4xMTEtMC41NDEtMC4wMDQtMS4zNjUsMC4yMjktMS44NjUgICBjMS4xODgtMi41NjIsMi4yNDMtNi43NzEsMS4yMjQtMTIuOTczYy0xLjU5Mi05LjY4NCw0Ljk3NS0xMS4wOTgsNS4yNDktMTEuMTVjMC41NDMtMC4xMDIsMC45LTAuNjI1LDAuOC0xLjE2OCAgIEM1My42NTQsMC4yNzQsNTMuMTQtMC4wODIsNTIuNTksMC4wMTZ6IE0zMy43NDYsMTMuOTY0YzAuODUyLDAuNDQ1LDEuNjY3LDAuOTQzLDIuNDQzLDEuNDk2YzAuNDQ5LDAuMzIsMC40OSwwLjkyMiwwLjA5NywxLjMwOSAgIGMtMC4zOTYsMC4zODktMC43OTcsMC43NjgtMS4yMDQsMS4xMzdjLTAuNDA4LDAuMzcxLTAuOTg4LDAuMjgzLTEuMjE3LTAuMjE5Yy0wLjM0Ni0wLjc1Ni0wLjY5NS0xLjc5OS0wLjktMy4xNyAgIEMzMi44ODMsMTMuOTcsMzMuMjU4LDEzLjcxLDMzLjc0NiwxMy45NjR6IE0yNy43MjMsMTIuOTIyYzAuMDgzLTAuNTQ1LDAuNjMyLTAuOTAxLDEuMTY5LTAuNzc0YzAuMzIsMC4wNzYsMC42MzcsMC4xNiwwLjk1LDAuMjUgICBjMC41MywwLjE1NCwwLjk2OSwwLjc1LDEuMDE2LDEuMjk5YzAuMjA5LDIuNDMsMC44MjgsNC4xNTQsMS40MTUsNS4yODljMC4yNTQsMC40OSwwLjE1MywxLjEzOS0wLjI4NiwxLjQ3MSAgIGMtMC40NDksMC4zMzgtMC45LDAuNjY0LTEuMzU1LDAuOTgxYy0wLjQ1MywwLjMxNi0xLjA3NiwwLjE4OS0xLjM0My0wLjI5NUMyOC4zNDUsMTkuNDM2LDI3LjE3NiwxNi40NzMsMjcuNzIzLDEyLjkyMnogICAgTTIyLjE4NiwxMi42NTVjMC4wNDgtMC41NTEsMC41MDQtMS4wMzEsMC45OTQtMS4wNTljMC4yOTQtMC4wMTYsMC41OS0wLjAyNSwwLjg4OC0wLjAyNWMwLjMxMiwwLDAuNjIyLDAuMDEsMC45MjksMC4wMjUgICBjMC41MTUsMC4wMjksMC44MjUsMC41MDUsMC43NDEsMS4wNWMtMC42NDMsNC4xOCwwLjc0Miw3LjYxMywxLjg1NSw5LjU3NmMwLjI3MiwwLjQ4MSwwLjEzOSwxLjA4Ni0wLjMzOSwxLjM2NSAgIGMtMC40ODMsMC4yODEtMC45NywwLjU1NS0xLjQ1NSwwLjgxOGMtMC40ODUsMC4yNjItMS4xMjcsMC4wOTItMS4zOTItMC4zOTVDMjMuMzA3LDIxLjk5MiwyMS43MjQsMTguMDQ3LDIyLjE4NiwxMi42NTV6ICAgIE0xNy45NzYsMTIuNDk3YzAuNDI2LTAuMTMxLDAuODU3LTAuMjUsMS4yOTUtMC4zNTNjMC41MzctMC4xMjksMC45MjksMC4yMzgsMC44OTEsMC43ODljLTAuMzksNS42MjksMS4yMjcsOS43NDYsMi40NDIsMTEuOTczICAgYzAuMjY1LDAuNDg2LDAuMTAxLDEuMDU3LTAuNDAzLDEuMjgzYy0wLjUzMywwLjI0LTEuMDYzLDAuNDY5LTEuNTkxLDAuNjg4Yy0wLjUxLDAuMjEyLTEuMTIyLTAuMDI2LTEuMzM4LTAuNTM2bDAsMCAgIGMtMC45NjMtMi4yNjYtMi40MjQtNi43MDktMi4yODQtMTIuNTI5QzE3LjAwMiwxMy4yNjEsMTcuNDQ4LDEyLjY2LDE3Ljk3NiwxMi40OTd6IE0xMi4zNjUsMTUuMTc5ICAgYzAuNTU5LTAuMzc5LDEuMTM4LTAuNzMsMS43MzQtMS4wNTVjMC40ODUtMC4yNjQsMC44NzctMC4wMSwwLjg3NywwLjU0M2MwLjAwOCw1LjY5NSwxLjQyLDEwLjAzMywyLjQyLDEyLjM4OSAgIGMwLjIxNiwwLjUwOC0wLjAxLDEuMDY1LTAuNTMyLDEuMjQ0Yy0wLjU1NCwwLjE5MS0xLjEsMC4zNzEtMS42MzcsMC41NDFjLTAuNTI2LDAuMTY2LTEuMjIxLTAuMDY3LTEuNDg4LTAuNTUyICAgYy0wLjkzOS0xLjY5My0yLjI3OC01LjIyNi0yLjIxLTExLjUzMUMxMS41MzUsMTYuMjA1LDExLjkwNywxNS40ODgsMTIuMzY1LDE1LjE3OXogTTcuMzU3LDE5LjkgICBjMC40NTktMC42MDIsMC45NS0xLjE3OCwxLjQ3MS0xLjcyOWMwLjM3OS0wLjQsMC43MDQtMC4yNjEsMC43MjEsMC4yOTJjMC4xNTQsNS4xOTUsMS4yNTEsOC40NzUsMi4yMTUsMTAuMzc3ICAgYzAuMjQ5LDAuNDkyLDAuMDU1LDAuOTg4LTAuNDgyLDEuMTIzYy0wLjU0OCwwLjEzNy0xLjA3OSwwLjI2NC0xLjU5LDAuMzc5Yy0wLjUzOCwwLjEyMy0xLjI0OS0wLjE0Ni0xLjQ3Ni0wLjY0OSAgIGMtMC45ODItMi4xODQtMS4zMDUtNi4xMzctMS40MDQtNy45ODRDNi43ODMsMjEuMTU4LDcuMDIyLDIwLjM0LDcuMzU3LDE5Ljl6IE00LjY5LDI0LjU4OWMwLjIxLTAuNTEyLDAuNDE1LTAuNDY3LDAuNDU4LDAuMDg0ICAgYzAuMTc2LDIuMjkzLDAuNjY4LDQuMDg3LDEuMTQ4LDUuMzU2YzAuMTk1LDAuNTE3LTAuMDU1LDEuMDA0LTAuNjAxLDEuMDkzYy0wLjU4OSwwLjA5Ni0xLjEwOCwwLjE3LTEuNTUxLDAuMjI5ICAgYy0wLjU0NywwLjA3MS0wLjk3MS0wLjMyNi0wLjkxOC0wLjg3N0MzLjQyOSwyOC40MSwzLjkzLDI2LjQzNSw0LjY5LDI0LjU4OXogTTMuNjY0LDM3LjMwMWMtMC4yMTMtMC45MTYtMC4zNjMtMS44NTYtMC40NS0yLjgxMyAgIGMtMC4wNS0wLjU1MSwwLjM3OC0xLjA0MSwwLjkyNS0xLjEwNmM1LjE2NC0wLjYyNywyMS43NjEtMy40OTYsMzMuNjUzLTE1LjI4NWMwLjM5NC0wLjM4OSwwLjYwNi0wLjgwNSwwLjQ4OS0wLjkxOCAgIGMtMC4xMTgtMC4xMTMsMC4xMjEsMC4wOTIsMC41MTQsMC40NzljMC42MTgsMC42MDksMS4xOTgsMS4yNTYsMS43MzYsMS45MzhjMC4zNDMsMC40MzMsMC4zMzIsMS4xNTctMC4wMTQsMS41ODcgICBDMjkuNjM0LDM0LjczNCwxMC44MjIsMzcuNjA3LDQuOTA4LDM4LjE4NUM0LjM1OSwzOC4yMzgsMy43ODgsMzcuODQsMy42NjQsMzcuMzAxeiBNNi43MjIsNDQuMjc1ICAgYy0wLjY2OS0wLjk4My0xLjI1OC0yLjAyNi0xLjc1NC0zLjEyMWMtMC4yMjgtMC41MDIsMC4wNTYtMC45NTUsMC42MDUtMS4wMWM2LjU5NC0wLjY1NCwyNC44MzctMy42NjgsMzYuMDczLTE3LjE4OCAgIGMwLjM1NC0wLjQyNCwwLjg1NC0wLjM5MSwxLjEwNSwwLjFjMC4zNzcsMC43MzQsMC43MTUsMS40OTIsMS4wMDYsMi4yNzNjMC4xOSwwLjUxOCwwLjA3MSwxLjMxNi0wLjI1LDEuNzY2ICAgQzM2LjYzMywzNi42NDQsMjYuNTMxLDQxLjEzMSwxOC42NSw0My4yNGMtMC41MzMsMC4xNDItMS4wNDksMC4yNS0xLjE0OCwwLjI1Yy0wLjEwMSwwLTAuMTgyLDAuMDIxLTAuMTgxLDAuMDQzICAgYzAuMDAxLDAuMDI1LTAuNDM0LDAuMTUtMC45NzMsMC4yNzFjLTMuNTA1LDAuNzg2LTYuMzgsMS4xLTguMDQ3LDEuMjIzQzcuNzUsNDUuMDY4LDcuMDMyLDQ0LjczMiw2LjcyMiw0NC4yNzV6IE0xMy4wMzcsNTAuMzYyICAgYy0xLjIzNi0wLjc3MS0yLjM4NC0xLjY2OC0zLjQzMS0yLjY3Yy0wLjM5OS0wLjM4Mi0wLjI1OS0wLjc0NSwwLjI5LTAuODA0YzAuNDgyLTAuMDUsMS4wMTItMC4xMTEsMS41ODQtMC4xODkgICBjMC41NDgtMC4wNzEsMS4wNTcsMC4zMDQsMS4xNzgsMC44NDNjMC4yMSwwLjkyOCwwLjQ5LDEuNzM1LDAuNzk3LDIuNDMyQzEzLjY4LDUwLjQ3NywxMy41MDYsNTAuNjUzLDEzLjAzNyw1MC4zNjJ6ICAgIE0xOC43NjEsNTIuODIzYy0wLjM4Ny0wLjEwNC0wLjc2OC0wLjIxOS0xLjE0NS0wLjM0NmMtMC41MjMtMC4xNzMtMS4yMDgtMC42OTYtMS40NzktMS4xOGMtMC40NTgtMC44MTItMS4xMDctMi4xOTgtMS41MTQtNC4wODYgICBjLTAuMTE2LTAuNTM5LDAuMjYxLTEuMDYzLDAuODAyLTEuMTc0YzAuMzM2LTAuMDY3LDAuNjgtMC4xNDEsMS4wMjgtMC4yMTdjMC41MzktMC4xMTksMS4wMTcsMC4yMjMsMS4wOTcsMC43NyAgIGMwLjM0MSwyLjM0NSwxLjAyNSw0LjIwOSwxLjcwOSw1LjU4NkMxOS41MDUsNTIuNjcsMTkuMjk0LDUyLjk2NywxOC43NjEsNTIuODIzeiBNMjUuNDkzLDUzLjQ2ICAgYy0wLjQ3MSwwLjAzNS0wLjk0NSwwLjA1Ny0xLjQyNSwwLjA1N2MtMC4yODIsMC0wLjU2Mi0wLjAxLTAuODQyLTAuMDI1Yy0wLjQ2My0wLjAyOS0xLjEyMS0wLjQwOC0xLjQyLTAuODczICAgYy0wLjc2Ny0xLjE4NS0xLjg4My0zLjM3My0yLjMwNy02LjUyM2MtMC4wNzQtMC41NDksMC4zMjQtMS4xMTEsMC44NTQtMS4yNjZjMC42NjktMC4xOTMsMS4zNTEtMC40MDQsMi4wNDItMC42MzQgICBjMC41MjUtMC4xNzIsMS4wMjMsMC4xMTksMS4xMzEsMC42NjJjMC43MzgsMy43MiwxLjY2Nyw2LjEyMywyLjQ2NCw3LjY0QzI2LjI0Nyw1Mi45ODQsMjYuMDQ0LDUzLjQxOSwyNS40OTMsNTMuNDZ6ICAgIE0zMS42MjMsNTIuMDkyYy0wLjY0MywwLjI1LTEuMzAxLDAuNDY3LTEuOTc0LDAuNjUyYy0wLjUzMiwwLjE0Ny0xLjI1Mi0wLjEwNi0xLjUzOC0wLjU4Yy0wLjc0NC0xLjIzMi0xLjg0My0zLjY1LTIuNjgtOC4wMTcgICBjLTAuMTA0LTAuNTQxLDAuMjM3LTEuMTQ2LDAuNzQ4LTEuMzU0YzAuNjg2LTAuMjgzLDEuMzc1LTAuNTg0LDIuMDY2LTAuOTA0YzAuNTAyLTAuMjMyLDAuOTQ0LDAuMDE2LDEuMDEyLDAuNTY0ICAgYzAuNTQyLDQuMzc1LDEuNjg5LDYuOTczLDIuNjg4LDguNDU5QzMyLjI1NCw1MS4zNywzMi4xMzgsNTEuODkyLDMxLjYyMyw1Mi4wOTJ6IE0zNy4zODgsNDguNzAyICAgYy0wLjY3MiwwLjU1Ny0xLjM3OSwxLjA3My0yLjExNiwxLjU0NWMtMC40NjYsMC4yOTctMS4xODEsMC4yMDItMS41MDMtMC4yNDRjLTAuODc1LTEuMjE3LTIuMTIzLTMuNzMyLTIuNjEzLTguNTM1ICAgYy0wLjA1Ny0wLjU0OSwwLjMwNy0xLjIwOSwwLjc4NS0xLjQ4M2MwLjQ4NC0wLjI3NiwwLjk2OS0wLjU2MywxLjQ0OS0wLjg2MmMwLjQ3MS0wLjI5MSwwLjg1My0wLjA5MSwwLjkwMSwwLjQ2MSAgIGMwLjMzMiwzLjY0MywxLjkyMSw2LjIxNywzLjE4MSw3LjcyM0MzNy44MjcsNDcuNzI3LDM3LjgxNCw0OC4zNSwzNy4zODgsNDguNzAyeiBNNDEuNzkyLDQzLjcxMyAgIGMtMC40NzksMC43NTQtMS4wMDcsMS40NzYtMS41NzUsMi4xNmMtMC4zNTMsMC40MjQtMC45NzIsMC40MzctMS4zMTgsMC4wMDZjLTEuMTc2LTEuNDU1LTIuNjcyLTQuMDI4LTIuNjc0LTcuNjk2ICAgYzAtMC41NTIsMC4zOTUtMS4yNjcsMC44My0xLjYwNmMwLjUxLTAuMzk2LDEuMDE3LTAuODA3LDEuNTE5LTEuMjM0YzAuNDIxLTAuMzU2LDAuNzY5LTAuMjA5LDAuODIxLDAuMzQzICAgYzAuMzA2LDMuMTQ0LDEuMzkzLDUuMjA5LDIuMjczLDYuNDAxQzQxLjk5Niw0Mi41MzIsNDIuMDg4LDQzLjI0Nyw0MS43OTIsNDMuNzEzeiBNNDMuNjYzLDM5Ljk5NSAgIGMtMC4xOTYsMC41MTYtMC42NTEsMC41NjctMC45MjUsMC4wODhjLTAuNzI3LTEuMjczLTEuNDY0LTMuMzE2LTEuNDMyLTYuMzI0YzAuMDA2LTAuNTUzLDAuMzUzLTEuMzE4LDAuNzI5LTEuNzIzICAgYzAuNi0wLjY0NiwxLjE4Ni0xLjMxNCwxLjc1My0yLjAxN2MwLjM0OS0wLjQyOSwwLjY4OC0wLjg1NCwwLjc3MS0wLjk0YzAuMDgyLTAuMDg5LDAuMjI3LDAuMjgsMC4zLDAuODI3ICAgYzAuMTE0LDAuODYzLDAuMTgzLDEuNzQyLDAuMTgzLDIuNjM4QzQ1LjA0MSwzNS4xNjksNDQuNTUxLDM3LjY3Niw0My42NjMsMzkuOTk1eiIgZmlsbD0iI0ZGRkZGRiIvPgo8L2c+CjxnPgo8L2c+CjxnPgo8L2c+CjxnPgo8L2c+CjxnPgo8L2c+CjxnPgo8L2c+CjxnPgo8L2c+CjxnPgo8L2c+CjxnPgo8L2c+CjxnPgo8L2c+CjxnPgo8L2c+CjxnPgo8L2c+CjxnPgo8L2c+CjxnPgo8L2c+CjxnPgo8L2c+CjxnPgo8L2c+Cjwvc3ZnPgo=',
          commands: [
            {
              command: 'npm install === yarn',
              description: 'Install is the default behavior'
            },
            {
              command: 'npm install [package] --save === yarn add [package]',
              description: 'Save package tp package.json'
            },
            {
              command: 'npm install [package] --save === yarn add [package]',
              description: 'Save package to package.json'
            },
            {
              command: 'npm install taco --save-dev === yarn add taco --dev',
              description: 'Save package to dev dependencies'
            },
            {
              command: 'npm uninstall [package] --save === yarn remove [package]',
              description: 'Remove package from package.json'
            },
            {
              command: 'npm update --save === yarn upgrade',
              description: 'Upgrades packages and package.json version numnbers'
            },
            {
              command: 'npm install taco --global === yarn global add taco',
              description: 'Global install (use global flag with care)'
            }
          ]
        },
        {
          name: 'Vim',
          commands: [
            {
              command: ':help keyword',
              description: 'Open help for keyword'
            },
            {
              command: 'cc',
              description: 'Change (replace) entire line'
            },
            {
              command: 'cw',
              description: 'Change (replace) to the end of the word'
            },
            {
              command: 'u',
              description: 'Undo'
            },
            {
              command: 'Ctrl + r',
              description: 'Redo'
            },
            {
              command: 'H',
              description: 'Move to top of screen'
            },
            {
              command: 'G',
              description: 'Go to the last line of the document'
            },
            {
              command: 'e',
              description: 'Jump forwards to the end of a word'
            },
            {
              command: 'b',
              description: 'Jump backwards to the start of a word'
            },
            {
              command: 'Ctrl + d',
              description: 'Move forward 1/2 a screen'
            },
            {
              command: 'Ctrl + u',
              description: 'Move back 1/2 a screen'
            },
            {
              command: 'i',
              description: 'Insert before the cursor'
            },
            {
              command: 'A',
              description: 'Insert (append) at the end of the line'
            },
            {
              command: 'ea',
              description: 'Insert (append) at the end of the word'
            }
          ]
        },
        {
          name: 'Docker',
          icon: 'data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0idXRmLTgiPz4KPCEtLSBHZW5lcmF0b3I6IEFkb2JlIElsbHVzdHJhdG9yIDE5LjIuMSwgU1ZHIEV4cG9ydCBQbHVnLUluIC4gU1ZHIFZlcnNpb246IDYuMDAgQnVpbGQgMCkgIC0tPgo8c3ZnIHZlcnNpb249IjEuMSIgaWQ9IkxheWVyXzEiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIgeG1sbnM6eGxpbms9Imh0dHA6Ly93d3cudzMub3JnLzE5OTkveGxpbmsiIHg9IjBweCIgeT0iMHB4IgoJIHZpZXdCb3g9IjAgMCA0MSAzNC41IiBzdHlsZT0iZW5hYmxlLWJhY2tncm91bmQ6bmV3IDAgMCA0MSAzNC41OyIgeG1sOnNwYWNlPSJwcmVzZXJ2ZSI+CjxzdHlsZSB0eXBlPSJ0ZXh0L2NzcyI+Cgkuc3Qwe2ZpbGw6I0ZGRkZGRjt9Cgkuc3Qxe2NsaXAtcGF0aDp1cmwoI1NWR0lEXzRfKTt9Cjwvc3R5bGU+CjxnPgoJPGc+CgkJPGc+CgkJCTx0aXRsZT5Hcm91cCAzPC90aXRsZT4KCQkJPGRlc2M+Q3JlYXRlZCB3aXRoIFNrZXRjaC48L2Rlc2M+CgkJCTxnPgoJCQkJPGc+CgkJCQkJPGc+CgkJCQkJCTxwYXRoIGlkPSJTVkdJRF8xXyIgY2xhc3M9InN0MCIgZD0iTTguNywyNGMtMS4xLDAtMi4xLTAuOS0yLjEtMnMwLjktMiwyLjEtMnMyLjEsMC45LDIuMSwyUzkuOCwyNCw4LjcsMjRMOC43LDI0eiBNMzQuNSwxMy4xCgkJCQkJCQljLTAuMi0xLjYtMS4yLTIuOS0yLjUtMy45bC0wLjUtMC40bC0wLjQsMC41Yy0wLjgsMC45LTEuMSwyLjUtMSwzLjdjMC4xLDAuOSwwLjQsMS44LDAuOSwyLjVjLTAuNCwwLjItMC45LDAuNC0xLjMsMC42CgkJCQkJCQljLTAuOSwwLjMtMS44LDAuNC0yLjcsMC40SDEuMUwxLDE3LjFDMC44LDE5LDEuMSwyMSwxLjksMjIuOGwwLjQsMC43djAuMWMyLjQsNCw2LjcsNS44LDExLjQsNS44YzksMCwxNi40LTMuOSwxOS45LTEyLjMKCQkJCQkJCWMyLjMsMC4xLDQuNi0wLjUsNS43LTIuN2wwLjMtMC41bC0wLjUtMC4zQzM3LjgsMTIuOCwzNiwxMi43LDM0LjUsMTMuMUwzNC41LDEzLjF6IE0yMS42LDExLjVoLTMuOXYzLjloMy45VjExLjV6IE0yMS42LDYuNgoJCQkJCQkJaC0zLjl2My45aDMuOVY2LjZ6IE0yMS42LDEuNmgtMy45djMuOWgzLjlWMS42eiBNMjYuNCwxMS41aC0zLjl2My45aDMuOVYxMS41eiBNMTEuOSwxMS41SDh2My45aDMuOVYxMS41eiBNMTYuOCwxMS41aC0zLjkKCQkJCQkJCXYzLjloMy45VjExLjV6IE03LjEsMTEuNUgzLjJ2My45aDMuOUw3LjEsMTEuNUw3LjEsMTEuNXogTTE2LjgsNi42aC0zLjl2My45aDMuOVY2LjZ6IE0xMS45LDYuNkg4djMuOWgzLjlWNi42eiIvPgoJCQkJCTwvZz4KCQkJCQk8Zz4KCQkJCQkJPGRlZnM+CgkJCQkJCQk8cGF0aCBpZD0iU1ZHSURfMl8iIGQ9Ik04LjcsMjRjLTEuMSwwLTIuMS0wLjktMi4xLTJzMC45LTIsMi4xLTJzMi4xLDAuOSwyLjEsMlM5LjgsMjQsOC43LDI0TDguNywyNHogTTM0LjUsMTMuMQoJCQkJCQkJCWMtMC4yLTEuNi0xLjItMi45LTIuNS0zLjlsLTAuNS0wLjRsLTAuNCwwLjVjLTAuOCwwLjktMS4xLDIuNS0xLDMuN2MwLjEsMC45LDAuNCwxLjgsMC45LDIuNWMtMC40LDAuMi0wLjksMC40LTEuMywwLjYKCQkJCQkJCQljLTAuOSwwLjMtMS44LDAuNC0yLjcsMC40SDEuMUwxLDE3LjFDMC44LDE5LDEuMSwyMSwxLjksMjIuOGwwLjQsMC43djAuMWMyLjQsNCw2LjcsNS44LDExLjQsNS44YzksMCwxNi40LTMuOSwxOS45LTEyLjMKCQkJCQkJCQljMi4zLDAuMSw0LjYtMC41LDUuNy0yLjdsMC4zLTAuNWwtMC41LTAuM0MzNy44LDEyLjgsMzYsMTIuNywzNC41LDEzLjFMMzQuNSwxMy4xeiBNMjEuNiwxMS41aC0zLjl2My45aDMuOVYxMS41eiBNMjEuNiw2LjYKCQkJCQkJCQloLTMuOXYzLjloMy45VjYuNnogTTIxLjYsMS42aC0zLjl2My45aDMuOVYxLjZ6IE0yNi40LDExLjVoLTMuOXYzLjloMy45VjExLjV6IE0xMS45LDExLjVIOHYzLjloMy45VjExLjV6IE0xNi44LDExLjVoLTMuOQoJCQkJCQkJCXYzLjloMy45VjExLjV6IE03LjEsMTEuNUgzLjJ2My45aDMuOUw3LjEsMTEuNUw3LjEsMTEuNXogTTE2LjgsNi42aC0zLjl2My45aDMuOVY2LjZ6IE0xMS45LDYuNkg4djMuOWgzLjlWNi42eiIvPgoJCQkJCQk8L2RlZnM+CgkJCQkJCTxjbGlwUGF0aCBpZD0iU1ZHSURfNF8iPgoJCQkJCQkJPHVzZSB4bGluazpocmVmPSIjU1ZHSURfMl8iICBzdHlsZT0ib3ZlcmZsb3c6dmlzaWJsZTsiLz4KCQkJCQkJPC9jbGlwUGF0aD4KCQkJCQkJPGcgY2xhc3M9InN0MSI+CgkJCQkJCQk8Zz4KCQkJCQkJCQk8Zz4KCQkJCQkJCQkJPHJlY3QgaWQ9IlNWR0lEXzNfIiB4PSItNDguOCIgeT0iLTIxIiBjbGFzcz0ic3QwIiB3aWR0aD0iMTI3NC44IiBoZWlnaHQ9IjE1MS40Ii8+CgkJCQkJCQkJPC9nPgoJCQkJCQkJPC9nPgoJCQkJCQk8L2c+CgkJCQkJPC9nPgoJCQkJPC9nPgoJCQk8L2c+CgkJPC9nPgoJPC9nPgo8L2c+Cjwvc3ZnPgo=',
          commands: [
            {
              command: 'docker build -t myapp:1.0 .',
              description: 'Build an image from the Dockerfile in the current directory and tag the image'
            },
            {
              command: 'docker images',
              description: 'List all images that are locally stored with the Dockerengine'
            },
            {
              command: 'docker rmi alpine:3.4',
              description: 'Delete an image from the local image store'
            },
            {
              command: 'docker pull alpine:3.4',
              description: 'Pull an image from a registry'
            },
            {
              command: 'docker tag alpine:3.4 myrepo/myalpine:3.4',
              description: 'Retag a local image with a new image name and tag'
            },
            {
              command: 'docker login my.registry.com:8000',
              description: 'Log in to a registry (the Docker Hub by default)'
            },
            {
              command: 'docker push myrepo/myalpine:3.4',
              description: 'Push an image to a registry'
            },
            {
              command: 'docker run --rm',
              description: 'Remove container automatically after it exits'
            },
            {
              command: 'docker run -p 5000:80',
              description: 'Expose port 5000 externally and map to port 80'
            },
            {
              command: 'docker run alpine:3.4',
              description: 'The image from which the container is instantiated'
            },
            {
              command: 'docker run --name web',
              description: 'Name the container'
            },
            {
              command: 'docker run /bin/sh',
              description: 'The command to run inside the container'
            },
            {
              command: 'docker stop web',
              description: 'Stop a running container through SIGTERM'
            },
            {
              command: 'docker kill web',
              description: 'Stop a running container through SIGKILL'
            },
            {
              command: 'docker network create --subnet 10.1.0.0/24 --gateway 10.1.0.1 -d overlay mynet',
              description: 'Create an overlay network and specify a subnet'
            },
            {
              command: 'docker network ls',
              description: 'List the networks'
            },
            {
              command: 'docker ps',
              description: 'List the running containers'
            },
            {
              command: 'docker rm -f $(docker ps -aq)',
              description: 'Delete all running and stopped containers'
            },
            {
              command: 'docker exec -it web bash',
              description: 'Create a new bash process inside the container and connect it to the terminal'
            },
            {
              command: 'docker logs --tail 100 web',
              description: 'Print the last 100 lines of a container’s logs'
            }
          ]
        }
      ]
    }
  }
</script>

<style>
body {
  background: #FFF;
}
.container {
  margin: 0;
  padding: 0;
}
</style>
