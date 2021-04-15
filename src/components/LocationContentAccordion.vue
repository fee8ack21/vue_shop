<template>
  <li class="location-accordion">
    <a
      href="#"
      class="accordion-title d-block py-1 text-center text-decoration-none"
      @click.prevent="accordionState = !accordionState"
      >桃園市</a
    >
    <ul class="list-unstyled" :class="{ active: accordionState }">
      <li><a href="#" class="d-block text-decoration-none bg-secondary">1</a></li>
      <li><a href="#" class="d-block text-decoration-none bg-secondary">1</a></li>
      <li><a href="#" class="d-block text-decoration-none bg-secondary">1</a></li>
    </ul>
  </li>
</template>

<script>
export default {
  name: 'LocationContentAccordion',
  data() {
    return { accordionState: false };
  },
};
</script>
<style lang="scss">
.location-accordion {
  .accordion-title {
    font-size: 16px;
    border : {
      bottom: 1px solid #ced4da;
    }
  }
  ul {
    max-height: 0px;
    overflow: hidden;
    transition: 0.15s;
    background-color: lightblue;
  }
  ul.active {
    max-height: 300px;
  }
}
</style>
