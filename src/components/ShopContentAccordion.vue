<template>
  <li class="shop-accordion-item">
    <a href="#" @click="accordionState = !accordionState">Category</a>
    <ul class="list-unstyled" :class="{ active: accordionState }">
      <li><a href="#">1</a></li>
      <li><a href="#">1</a></li>
      <li><a href="#">1</a></li>
    </ul>
  </li>
</template>

<script>
export default {
  name: 'ShopContentAccordion',
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
