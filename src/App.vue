<template>
<Conversor/>
</template>

<script>
import Conversor from  './components/Conversor';

export default {

  name: 'App',
  components: {
    Conversor

  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@100;400;700&display=swap');
html{
  font-family: 'Roboto', sans-serif;
}
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
input::placeholder{
  font-family: 'Roboto', sans-serif;
  color: white;
}
</style>
