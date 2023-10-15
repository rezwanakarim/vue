<template>
<div >{{greet}} {{ name}}</div>
<div v-text ="greet"></div>
<div v-html ="greet1"></div>
<div v-html ="hack"></div>
<h1 v-bind:i="headingId">Heading</h1>
<button v-bind:disabled="isDisabled">click</button>
<h2 class="underline">Text in underlined</h2> 
<h2 class="underline" v-bind:class="status"> Status</h2>
<h2 v-bind:class="isPromoted && 'promoted'">Promoted</h2>
<h3 v-bind:class="isSoldout ? 'sold-out' :'new'">Soldout ? movie</h3>
<h2 v-bind:class ="['new','promoted']"> Array Binding</h2>
<h2 v-bind:class ="[isPromoted && 'promoted', isSoldout ? 'sold-out' :'new']"> Array Binding</h2>
<h1 v-bind:class ="{
  promoted: isPromoted,
  new : !isSoldout,
  'sold-out': isSoldout
}">Object Conditional </h1>
<h1 v-bind:style="{
  color: highlightColor,
  'font-size': headerSize + 'px'
}"> Inline Style</h1>
</template>

<script>

export default {
  name: 'App',
  data(){
    return{
      name : "Rezwana",
      greet : "bye",
      greet1 : "<b>hi</b>",
      hack : `<a href="#" onclick="alert('hacked')"> Win<a/>`,
      headingId : "heading",
      isDisabled : true,
      status : "Danger",
      isPromoted : false,
      isSoldout : false,
      highlightColor : 'yellow',
      headerSize : 40
    };
  },
 
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.underline{
  text-decoration: underline;
}

.promoted{font-style: italic;}

.new{
  color: green;
}

.sold-out{
  color: red;
}

</style>
