<template>
  <div id="starship-enterprise">
    <h1>Reactive Style Specificity using custom attributes...</h1>
    <h2>A possible problem causing, yet simple hack.</h2>
    <p>Using non-props attributes or data-attributes to make parent CSS more specific in the case where parent adds colliding specificity to the child root.</p>
    <p><em><strong>Disclaimer</strong>: I don't recommend it because adding attributes to strong arm css control outside of the normal reactive JavaScript or CSS handling is not a well-known pattern, and this means possible confusion for teams or unexpected behavior on CSS. It may also prevent reusability of or confusion on how to override, with the "who's in charge" problem when inception nesting components or reverse nesting components. <a href="https://github.com/vuejs/vue-loader/issues/521">See here.</a></em></p>
    <p><strong>Demo</strong>: Open up the your browser developer inspector tools to see the child text being overriden by the parent component in the box below.</p>

    <picard class="css-control"></picard>
    <img src="./assets/question-from-wesley.jpg" width="50%" />

    <h3>child component</h3>
      <pre>
&lt;template&gt;
  &lt;p :class=&quot;$style.wesley&quot; :href=&quot;url&quot;&gt;Is it cool if my dance crew uses the holodeck to practice our new sick moves?&lt;/p&gt;
&lt;/template&gt;

&lt;style module&gt;
  .wesley {
    color: white;
    font-weight: bold;
    font-size: 3em;
    background:   linear-gradient(to bottom, #5f6028 0%, #5f6028 15%, #6b1112 15%, #6b1112 25%, #afba1d 25%, #afba1d 25%, #afba1d 35%, #16848e 35%, #16848e 45%, #a8a8a8 45%, #a8a8a8 100%);
  }
&lt;/style&gt;
      </pre>

    <h3>parent component</h3>
      <pre>
&lt;template&gt;
  &lt;wesley :class=&quot;$style.shutupwesley&quot; data-says-because-picard-said-make-it-so override&gt;&lt;/wesley&gt;
&lt;/template&gt;

&lt;style module&gt;
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
&lt;/style&gt;
      </pre>
  </div>
</template>

<script>
import picard from './picard.vue'

export default {
  name: 'app',
  components: { picard }
}
</script>

<style>
#starship-enterprise {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: block;
  text-align: center;
  padding: 3em;
  background-color: tan;
}
p,
pre {
  text-align: left;
}
pre {
  margin: 1em 0;
  padding: 1em;
  background: #efefef;
  display: block;
  color: #333;
  overflow-x: scroll;
}
.css-control {
  display: block;
  margin-bottom: 1em;
  padding: 2em;
  font-size: 2em;
}
.css-control a {
  text-decoration: none;
}
</style>
