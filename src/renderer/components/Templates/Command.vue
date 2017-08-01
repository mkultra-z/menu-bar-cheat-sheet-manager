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
  border-bottom: 1px solid #E6E6E6;
  padding-top: 1rem;
  padding-bottom: 1.2rem;
  max-width: 100%;
}
.command-code code {
  overflow-x:auto;
  white-space:nowrap;
  background: #6A8EAE;
  color: #8FF7C8;
  font-size: 12px;
  display: inline-block;
  max-width: 100%;
}
.description {
  color: #6A8EAE;
  font-size: 13px;
  margin-bottom: .5rem;
}
</style>


<script>
  export default {
    props: ['command', 'index']
  }
</script>
