<template>
  <div class="about">
    <div v-for="currency in data">
      <span>{{ currency.code }} - {{ currency.rate_float }}</span>
    </div>
  </div>
</template>

<script>
import {instance} from "@/api.js";

export default {
  data: function() {
    return {
      data: null,
    };
  },
  mounted: function() {
    instance.get("bpi/currentprice.json")
    .then(response => this.data = response.data.bpi);
  }
}
</script>