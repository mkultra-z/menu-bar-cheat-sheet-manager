<template>
  <div class="container row command">
    <div class="col-12 description">
      {{command.description}}
    </div>
    <div class="col-12 command-code">
      <code>{{command.command}}</code>
    </div>
  </div>
</template>

<style>
.command-code code::-webkit-scrollbar { 
  display: none; 
}
.command {
  border-bottom: 1px solid #424242;
  padding-top: 1rem;
  padding-bottom: 1.5rem;
  max-width: 100%;
}
.command-code code {
  overflow-x:auto;
  white-space:nowrap;
  background: #212121;
  color: cornflowerblue;
  font-size: 13px;  
}
.description {
  color: white;
  font-size: 13px;
  margin-bottom: .5rem;
}
</style>


<script>
  export default {
    props: ['command', 'index']
  }
</script>
