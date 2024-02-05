<script>
import axios from "axios";
export default {
  name: "App",
  data() {
    return {
      mails: "",
    };
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/random/mail")
      .then((response) => {
        console.log(response);
        this.mails = response.data.response;
      });
  },
};
</script>

<template>
  <div>
    <ol>
      <li v-for="mail in mails">
        {{ mails }}
      </li>
    </ol>
  </div>
</template>

<style></style>
