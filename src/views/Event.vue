<template>
  <div class="main">
    <div class="container">
      <h4>Event</h4>
      <div class="list-content">
        <h5>Event Modifiers</h5>
        <!-- the click event's propagation will be stopped -->
        <a @click.stop="clickA" class="btn">Click Stop</a>

        <!-- the submit event will no longer reload the page -->
        <form @submit.prevent="onSubmit" class="mt-4">
          <button type="submit" class="btn">Submit Prevent</button>
        </form>

        <!-- modifiers can be chained -->
        <div class="mt-4">
          <a v-on:click.stop.prevent="clickA" class="btn">Click Stop Prevent</a>
        </div>

        <!-- just the modifier -->
        <form v-on:submit.prevent class="mt-4">
          <button type="submit" class="btn">Submit Prevent</button>
        </form>

        <!-- use capture mode when adding the event listener -->
        <!-- i.e. an event targeting an inner element is handled here before being handled by that element -->
        <div v-on:click.capture="clickA" class="mt-4">
          <span class="btn">
            Click Div
          </span>
        </div>

        <!-- only trigger handler if event.target is the element itself -->
        <!-- i.e. not from a child element -->
        <!-- <div v-on:click.self="doThat">...</div> -->
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    clickA: function() {
      console.log("clickstop");
    },
    onSubmit: function() {
      console.log("form submited");
    },
  },
};
</script>

<style scoped>
.btn {
  border: 1px solid black;
  border-radius: 8px;
  padding: 8px;
}
</style>
