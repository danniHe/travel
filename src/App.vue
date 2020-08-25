<template>
  <div id="app">
    <!-- activated  deactivated exclude -->
    <keep-alive exclude="Detail">
      <router-view />
    </keep-alive>
  </div>
</template>

<script>
export default {
  name: "App",
};
</script>
