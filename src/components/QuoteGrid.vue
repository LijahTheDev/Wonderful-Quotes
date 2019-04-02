<template>
  <div class="row">
    <appQuote v-for="(quote, i) in quotes" :key="i" @click.native="deleteQuote(i)">{{quote}}</appQuote>
  </div>
</template>

<script>
import Quote from "./Quote";

export default {
  name: "QuoteGrid",
  props: ["quotes"],
  components: {
    appQuote: Quote
  },
  methods: {
    deleteQuote(index) {
      this.$emit("quoteDeleted", index);
    }
  }
};
</script>

<style scoped>
</style>