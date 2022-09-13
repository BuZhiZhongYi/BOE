<template>
  <div id="container">
    <!-- <div id="nav">
      <router-link
        v-for="item in routes"
        :key="item.path"
        :to="item.path"
        :class="{
          link: true,
          active: name === item.name,
        }"
      >
        {{ item.name }}
      </router-link>
    </div> -->
    <main>
      <router-view />
    </main>
  </div>
</template>
<script>
import { computed, defineComponent } from "vue";
import { useRouter, useRoute } from "vue-router";
export default defineComponent({
  setup() {
    const router = useRouter();
    const route = useRoute();
    console.log("router", router.getRoutes(), route);
    const routes = computed(() => {
      return router.getRoutes().filter((e) => e.meta?.isLink);
    });

    const currentRouteName = computed(() => route.name);

    return {
      routes,
      name: currentRouteName,
    };
  },
});
</script>
<style lang="scss">
#app {
  font-family: MicrosoftYaHei, Microsoft YaHei, Avenir, Helvetica, Arial,
    sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  height: 100%;
}

#container {
  display: flex;
  width: 100%;
  height: 100%;

  main {
    flex: 1;
    height: 100%;
    width: 100%;
    padding: 30px;
    box-sizing: border-box;
    background-color: rgba(242, 245, 247, 1);
  }
}
</style>
