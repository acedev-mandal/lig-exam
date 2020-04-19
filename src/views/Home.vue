<template>
  <div class="home">
    <div id="main-content">
      <HomeContents />
      <HomeSidebar />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HomeContents from "@/components/home-contents.vue";
import HomeSidebar from "@/components/home-sidebar.vue";

export default {
  name: "Home",
  components: {
    HomeContents,
    HomeSidebar
  }
};
</script>

<style lang="scss" scoped>
#main-content {
  width: 90%;
  display: block;
  margin: auto;

  &::after {
    content: "";
    clear: both;
    display: table;
  }
}
</style>
