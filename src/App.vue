<template>
  <div>
    <List msg="Hello Vue 2.6 in CodeSandbox!" />
  </div>
</template>

<script>
import List from "./components/List.vue";
export default {
  name: "App",
  components: {
    List,
  },
};
</script>


<style>
:root {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
}
</style>