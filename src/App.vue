<script setup>

import formApp from "./components/form.vue"
</script>

<template>
  <formApp/>
  
</template>

<script>
  export default{
    data(){
      formApp
    }
  }
</script>
<style >

:root{
  --oq: #fff;
  --qora: black;
  --mitalic: rgba(128, 128, 128, 0.22);
}
@font-face{
  font-family: "Poppins";
  src: url("../fonts/Poppins-Light.ttf");
}
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-weight: "Poppins";
  color: var(--qora);
  text-align: center;
  overflow-x: hidden;
}
body{
  background: var(--mitalic);
  color: var(--qora);
}
.container{
  width: 1300px;
  margin: 0 auto;
  padding: 1rem;
}  
</style>
