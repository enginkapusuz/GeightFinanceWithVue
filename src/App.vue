<template>
  <div>Hello {{ message }}</div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      message: "World"
    };
  }
},
async mounted(){
  const { text } = await (await fetch("/message")).json();
  this.message = text;
};
</script>
