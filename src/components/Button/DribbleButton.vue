<template>
  <div class="dribble-btn">
    <button class="btn">
      <i class="fa fa-plus icon"></i>

      {{ label }}
    </button>
  </div>
</template>
<script lang="ts">
import { defineComponent } from "vue";
export default defineComponent({
  props: {
    name: String,
    label: { type: String, required: true },
  },
});
</script>
<style lang="scss">
.dribble-btn {
  margin: 0 0 0 52px;
  .btn {
    cursor: pointer;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    padding: 10px 16px;
    gap: 8px;

    width: 100%;
    height: 40px;

    background: white;
    color: #4094f5;
    font-weight: 500;
    font-size: 16px;
    line-height: 125%;

    border: 1px solid #e3e3e8;
    border-radius: 8px;
    .icon {
      margin-right: 8px;
    }
  }
}
</style>
