<template>
  <div class="home">
    <DemoSPS  />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import DemoSPS from "@/views/DemoSPS.vue"; // @ is an alias to /src

@Component({
  components: {
    DemoSPS,
  }
})
export default class Home extends Vue {}
</script>
