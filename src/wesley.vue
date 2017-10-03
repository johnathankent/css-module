<template>
  <p :class="$style.wesley">Is it cool if my dance crew uses the holodeck to practice our new sick moves?</p>
</template>

<script>
  export default {
    name: 'wesley'
  }
</script>

<style module>
  .wesley {
    color: white;
    font-weight: bold;
    font-size: 3em;
    background: #a8a8a8;
    background:    -moz-linear-gradient(top, #5f6028 0%, #5f6028 15%, #6b1112 15%, #6b1112 25%, #afba1d 25%, #afba1d 25%, #afba1d 35%, #16848e 35%, #16848e 45%, #a8a8a8 45%, #a8a8a8 100%);
    background: -webkit-linear-gradient(top, #5f6028 0%, #5f6028 15%, #6b1112 15%, #6b1112 25%, #afba1d 25%, #afba1d 25%, #afba1d 35%, #16848e 35%, #16848e 45%, #a8a8a8 45%, #a8a8a8 100%);
    background:   linear-gradient(to bottom, #5f6028 0%, #5f6028 15%, #6b1112 15%, #6b1112 25%, #afba1d 25%, #afba1d 25%, #afba1d 35%, #16848e 35%, #16848e 45%, #a8a8a8 45%, #a8a8a8 100%);
  }
</style>
