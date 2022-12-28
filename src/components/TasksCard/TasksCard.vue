<template>
  <div class="tasks-card">
    <div class="card">
      <div class="card-header">
        <div class="header-top">
          <input type="checkbox" class="checkbox" />
          <h3 class="card-header-title">
            {{ title }}
          </h3>
        </div>
        <p v-if="hasSubTitle" class="subtitle">{{ subTitle }}</p>

        <TasksCardRow :items="items"></TasksCardRow>
        <DribbleButton v-if="hasButton" label="Add form"></DribbleButton>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import TasksCardRow from "../../components/TasksCardRow/TasksCardRow.vue";
import { defineComponent } from "vue";
import DribbleButton from ".././Button/DribbleButton.vue";
export default defineComponent({
  name: "TasksCard",
  components: {
    TasksCardRow,
    DribbleButton,
  },
  props: {
    items: {
      type: Array,
      required: true,
    },
    title: {
      type: String,
      required: true,
    },
    subTitle: {
      type: String,
      required: true,
    },
    hasSubTitle: {
      type: Boolean,
      required: true,
    },
    hasButton: {
      type: Boolean,
      required: true,
    },
  },
  data() {
    return {};
  },
});
</script>

<style lang="scss" scoped>
.tasks-card {
  width: 40%;
  margin: auto;
  margin-bottom: 16px;
  height: max-content;
  padding: 32px;
  gap: 24px;
  background: #ffffff;
  border-radius: 16px;
  .card {
    .card-header {
      .header-top {
        display: flex;
        align-items: flex-start;
        justify-content: flex-start;

        [type="checkbox"] {
          width: 24px;
          height: 24px;
          margin-right: 24px;
          color: #0d0c21;
          vertical-align: middle;
          -webkit-appearance: none;
          background: none;
          border: 0;
          outline: 0;
          flex-grow: 0;
          border-radius: 8px;
          background-color: #ffffff;
          transition: background 300ms;
          cursor: pointer;
        }

        [type="checkbox"]::before {
          content: "";
          color: transparent;
          display: block;
          width: inherit;
          height: inherit;
          border-radius: inherit;
          border: 0;
          background-color: transparent;
          background-size: contain;
          box-shadow: inset 0 0 0 1px #ccd3d8;
        }

        [type="checkbox"]:checked {
          background-color: currentcolor;
        }

        [type="checkbox"]:checked::before {
          box-shadow: none;
          background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E %3Cpath d='M15.88 8.29L10 14.17l-1.88-1.88a.996.996 0 1 0-1.41 1.41l2.59 2.59c.39.39 1.02.39 1.41 0L17.3 9.7a.996.996 0 0 0 0-1.41c-.39-.39-1.03-.39-1.42 0z' fill='%23fff'/%3E %3C/svg%3E");
        }

        .card-header-title {
          font-weight: 600;
          font-size: 18px;
          line-height: 135%;
          color: #0d0c21;
          margin: 0;
          padding-bottom: 10px;
          padding-top: 2px;
        }
      }
      .subtitle {
        margin-top: 0px;
        margin-bottom: 24px;
        font-weight: 500;
        font-size: 16px;
        line-height: 125%;
        color: #767b90;
        margin-left: 52px;
      }
    }
  }
}
</style>
