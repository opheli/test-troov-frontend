<template>
    <div>
      <navBar />
      <div class="container">
        <br />
        <Nuxt />
      </div>
    </div>
  </template>


<script>

import navBar from "@/components/TheHeader/navBar";

export default {
  components: { navBar },
};

</script>


  