<template>
  <main class="main-shop">
    <div class="container py-5">
      <div class="row">
        <div class="col-3">
          <ul class="shop-accordion list-unstyled">
            <li>
              <input type="search" class="form-control" />
            </li>
            <ShopContentAccordion />
            <li class="shop-accordion-item">
              <a href="#" @click="accordionState = !accordionState">Brand</a>
              <ul class="list-unstyled" :class="{ active: accordionState }">
                <li><a href="#">1</a></li>
                <li><a href="#">1</a></li>
                <li><a href="#">1</a></li>
              </ul>
            </li>
          </ul>
        </div>
        <div class="col-9" style="min-height:calc(100vh - 302px)">
          <div class="d-flex justify-content-between">
            <div class="d-flex align-items-center mr-5">
              <a href="#" class="text-decoration-none"
                >Sort
                <b-icon icon="triangle-fill" class="ml-2" style="transform:rotate(180deg)"></b-icon>
              </a>
            </div>
            <div class="d-flex align-items-center mr-auto">
              <a href="#" class="text-decoration-none"
                >Number
                <b-icon icon="triangle-fill" class="ml-2" style="transform:rotate(180deg)"></b-icon
              ></a>
            </div>
            <div class="d-flex">
              <p class="mb-0">Category：<span class="text-secondary">Pedal</span></p>
              <p class="mb-0 ml-5">Brand：<span class="text-secondary">Boss</span></p>
            </div>
          </div>
        </div>
      </div>
      <b-pagination
        class="d-flex justify-content-center"
        v-model="currentPage"
        :total-rows="rows"
        :per-page="perPage"
        first-number
        last-number
      ></b-pagination>
    </div>
  </main>
</template>

<script>
import ShopContentAccordion from './ShopContentAccordion.vue';

export default {
  name: 'ShopContent',
  data() {
    return {
      accordionState: false,
      rows: 100,
      perPage: 1,
      currentPage: 5,
    };
  },
  components: {
    ShopContentAccordion,
  },
};
</script>

<style lang="scss">
.main-shop {
  min-height: calc(100vh - 152px);
  & > div {
    min-height: calc(100vh - 152px);
  }
  .shop-accordion {
    & > li > a {
      display: block;
      border-bottom: 1px solid #2c3e50;
      padding: 6px 12px;
      text-decoration: none;
    }
    .shop-accordion-item {
      & > ul {
        max-height: 0px;
        overflow: hidden;
        transition: 0.15s;
      }
      & > ul.active {
        max-height: 500px;
      }
      li a {
        display: block;
        padding: 6px 12px;
        background-color: lightgray;
        text-decoration: none;
      }
    }
  }
}
</style>
