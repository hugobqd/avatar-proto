<template>
  <div>
    <pre>{{ !!persons.length }}</pre>
    <div
      class="List"
      style="display: flex; flex-wrap: wrap; flex-direction: column"
      v-if="!!persons.length"
    >
      <div
        v-for="person in persons"
        :key="person.id.value"
        style="padding: 4px; display: flex; align-items: center"
      >
        <AvatarComputed
          :name="person.name.first + ' ' + person.name.last"
          :id="parseNumberInString(person.phone)"
          style=""
        />
        <span>{{ person.name.first + " " + person.name.last }}</span>
        <code>{{ parseNumberInString(person.phone) }}</code>
      </div>
    </div>
  </div>
</template>

<script>
import { avatarColors } from "./avatar-colors.js";
import AvatarComputed from "./AvatarComputed";
export default {
  name: "HelloWorld",
  components: {
    AvatarComputed,
  },
  props: {},
  data: function () {
    return {
      avatarColors,
      persons: [],
    };
  },
  methods: {
    async getData() {
      try {
        let response = await fetch("https://randomuser.me/api/?results=100");
        const { results } = await response.json();
        console.log(results);
        this.persons = results;
      } catch (error) {
        console.log(error);
      }
    },
    parseNumberInString: function (string) {
      var number = string.match(/\d+/g);
      return parseInt(number.join(""), 10);
    },
  },
  created() {
    this.getData();
  },
};
</script>
