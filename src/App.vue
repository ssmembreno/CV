<template>
  <div class="app-container">
    <BotChat />
    <NavBar />
    <MainProjects />
    <aboutMe />
    <ContactUs />
    <CopyRigth />
  </div>
</template>

<script setup>
import NavBar from './components/NavBar.vue';
import MainProjects from './components/MainProjects.vue';
import aboutMe from './components/aboutMe.vue';
import ContactUs from './components/ContactUs.vue';
import CopyRigth from './components/copyRigth.vue';
import BotChat from './components/BotChat.vue';
</script>

<style>
.app-container {
  position: static;
  overflow: visible;
}
</style>