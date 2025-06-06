<template>
    <section class="bg-[#0f1126]">
        <hr class="accessory">
        <p class="text-center text-white mt-3.5 ">Samuel Membreño © Todos los derechos reservados. </p>
        <br>
    </section>
</template>

<style>
.accessory {
  height: 6px;
  background-image: radial-gradient(
    closest-side,
    hsl(180, 100%, 52%),
    hsla(0, 45%, 6%, 0) 100%);
  position: relative;
}
.accessory:after {
  position: absolute;
  top:  50%;
  left: 50%;
  display:block;
  background-color: hsl(0, 0%, 75%);
  height: 12px;
  width:  12px;
  margin-top:  -10px;
  margin-left: -10px;
  border-radius: 4px 0;
  border: 4px solid hsla(0, 0%, 100%, 0.35);
  background-clip: padding-box;
  box-shadow: -10px 10px 0 hsla(0, 0%, 100%, 0.15), 10px -10px 0 hsla(0, 0%, 100%, 0.15);
}
</style>

<script setup>

</script>