<template>
  <div class="wrap">
    <Header></Header>
    <Cooperation></Cooperation>
    <Price></Price>
    <Contactus></Contactus>
  </div>
</template>

<script>
import Header from "./components/Header";
import Cooperation from './components/Cooperation'
import Price from './components/Price'
import Contactus from './components/Contactus'
export default {
  components: {
    Header,
    Cooperation,
    Price,
    Contactus
  },
};
</script>

<style scoped>


</style>