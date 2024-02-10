<script>
import axios from "axios";
export default {
  name: "App",
  data() {
    return {
      mails: [],
    };
  },

  mounted() {
    for (let i = 0; i < 10; i++) {
      axios
        .get("https://flynn.boolean.careers/exercises/api/random/mail")
        .then((response) => {
          console.log(response);
          this.mails.push(response.data.response);
        });
    }
  },
};
</script>

<template>
  <div>
    <ol>
      <li v-for="mail in mails">{{ mail }}</li>
    </ol>
  </div>
</template>

<style></style>
