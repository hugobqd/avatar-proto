<template>
  <div class="Avatar" :style="{ backgroundColor: color }">
    <span data-part="initial">{{ initial }}</span>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    color: {
      type: String,
    },
    initial: {
      type: String,
    },
    picture: {
      type: String,
    },
  },
  created: function () {},
};
</script>

<style lang='scss' >
.Avatar {
  background-color: silver;
  display: inline-flex;
  width: 2em;
  height: 2em;
  align-items: center;
  justify-content: center;
  overflow: hidden;
  border-radius: 50%;
  color: white;

  [data-part="initial"] {
    font-weight: 500;
    letter-spacing: 0.025em;
  }
}
</style>