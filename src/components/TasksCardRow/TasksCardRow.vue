<template>
  <div>
    <div class="tasks-card-row" v-for="(item, index) in items" :key="index">
      <ul class="list">
        <li class="item">
          <h2 class="title" :class="{ 'is-maxed': item.isMaxed }">
            {{ item.title }}
          </h2>
          <span
            class="percentage"
            :class="{ 'is-maxed-percentage': item.isMaxed }"
          >
            {{ item.percentage }}%</span
          >
        </li>
      </ul>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
export default defineComponent({
  name: "TasksCardRow",
  props: {
    items: {
      type: Array,
      required: true,
    },
    data() {
      return {};
    },
  },
});
</script>

<style lang="scss" scoped>
.tasks-card-row {
  display: flex;
  flex-direction: row;
  align-items: center;
  padding: 8px 16px;
  height: 24px;
  background: #f8f8f8;
  border-radius: 8px;
  margin: 0 0 0 52px;
  margin-bottom: 8px;
  .list {
    width: 100%;
    padding-left: 0;
    .item {
      display: flex;
      align-items: center;
      justify-content: space-between;
      width: 100%;
      list-style: none;
      .title {
        font-weight: 600;
        font-size: 18px;
        line-height: 135%;
        color: #0d0c21;
        &.is-maxed {
          text-decoration-line: line-through;
          color: #95959d;
        }
      }
      .percentage {
        color: white;
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 0 8px 3px 8px;
        padding-top: 4px;
        width: max-content;
        min-width: 21px;
        height: 18px;
        background: #0d0c21;
        border-radius: 16px;
        font-weight: 600;
        font-size: 14px;
        line-height: 140%;
        &.is-maxed-percentage {
          background: #ebebeb;
          color: #95959d;
        }
      }
    }
  }
}
</style>
