<template>
  <Avatar class="AvatarComputed" :initial="'XD'" :color="'#C00FFE'" />
</template>

<script>
import Avatar from "./Avatar";
import { avatarInitials } from "./avatar-initials.js";
export default {
  name: "HelloWorld",
  components: {
    Avatar,
  },
  props: {
    id: {
      type: Number,
    },
    name: {
      type: String,
    },
    picture: {
      type: String,
    },
  },
  computed: {},
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