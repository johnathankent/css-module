<template>
  <!-- Add custom data-attr or non-prop attribute here -->
  <wesley :class="$style.shutupwesley" data-says-because-picard-said-make-it-so override></wesley>
</template>

<script>
  import wesley from './wesley.vue'

  export default {
    name: 'picard',
    components: { wesley }
  }
</script>

<style module>
  /* CSS more specific than child */
  .shutupwesley[data-says-because-picard-said-make-it-so] {
    color: firebrick;
    background: firebrick;
    border-top: 1em solid black;
  }
  /* This works, too! But it is non-valid HTML. Would require registering the attribute to HTML doc. */
  .shutupwesley[override] {
    font-size: smaller;
  }
</style>
