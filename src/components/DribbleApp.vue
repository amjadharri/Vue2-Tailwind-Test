<template>
  <div class="hello">
    <DribbleHeader
      class="dribble-header"
      :logo="require('@/assets/dribbble-logo-1.png')"
      :title="title"
      :subTitle="subTitle"
      :user="userName"
      :avatar="require('@/assets/avatar.png')"
    />

    <div class="cards-container">
      <TasksCard
        :title="tasksCard.title"
        :subTitle="tasksCard.subTitle"
        :hasButton="tasksCard.hasButton"
        :hasSubTitle="true"
        :items="items"
      />
      <TasksCard
        :title="taskCard2.title"
        :subTitle="taskCard2.subTitle"
        :hasButton="tasksCard.hasButton"
        :hasSubTitle="false"
        :items="items2"
      />
      <TasksCard :hasSubTitle="false" :title="taskCard3.title" />
    </div>
  </div>
</template>

<script lang="ts">
import DribbleHeader from "@/components/Header/DribbleHeader.vue";
import TasksCard from "@/components/TasksCard/TasksCard.vue";
import Vue from "vue";

export default Vue.extend({
  name: "DribbleApp",
  components: {
    DribbleHeader,
    TasksCard,
  },
  data() {
    return {
      title: "Hosting a dribble meetup",
      logo: "../../assets/dribbble-logo-1.png",

      subTitle: "You were invited to participate in",
      userName: "machiavelli",
      avatar: "../../assets/avatar.png",
      tasksCard: {
        hasButton: true,
        title: "Prepare KYC document for all managing directors",
        subTitle: "Please note that all documents need to be do asap",
      },
      taskCard2: {
        hasButton: true,
        title: "Sign the forms",
        subTitle: "Please note that all forms need to be do asap",
      },
      taskCard3: {
        hasButton: false,
        title: "Sign the Term Sheet",
      },
      items: [
        {
          title: "Identity details",
          percentage: 0,
          isMaxed: false,
        },
        {
          title: "Address details",
          percentage: 100,
          isMaxed: true,
        },
        {
          isMaxed: true,
          title: "File upload",
          percentage: 100,
        },
      ],
      items2: [
        {
          title: "Term Sheet",
          percentage: 0,
          isMaxed: false,
        },
      ],
    };
  },
});
</script>

<style scoped lang="scss">
.hello {
  .dribble-header {
    position: relative;
  }
  .cards-container {
    position: absolute;
    width: 100%;
    margin-top: -52px;
    z-index: 99;
  }
}
</style>
