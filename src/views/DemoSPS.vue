<template>
  <div>
    <div>SPS:<input type="text" v-model="value">
      <button @click="parse">ok</button>
    </div>
    <div>Result:{{result}}</div>
  </div>
</template>

<script>
  import SPSParser from "../h264/demux/sps-parser";

  /**
   * 十六进制转 bytearray
   */
  const hex2ab = function (hex) {
    const typedArray = new Uint8Array(hex.match(/[\da-f]{2}/gi).map(function (h) {
      return parseInt(h, 16)
    }))

    const buffer = typedArray.buffer
    return buffer
  };
  export default {
    name: "DemoSPS",
    data: function () {
      return {
        result: '',
        value: '',
      }
    },
    methods: {
      parse: function () {
        this.result = SPSParser.parseSPS(new Uint8Array(hex2ab(this.value)));
      }
    }
  }
</script>

<style scoped>

</style>
