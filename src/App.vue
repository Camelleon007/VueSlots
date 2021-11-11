<template>
  <!-- <the-header></the-header> -->
  <TheHeader />
  <BadgeList />
  <UserInfo
    :full-name="activeUser.name"
    :info-text="activeUser.description"
    :role="activeUser.role"
  />
  <CourseGoals>
    <template #default="goalsProps">
      <h2>{{ goalsProps.item }}</h2>
      <p>{{ goalsProps["item-key"] }}</p>
    </template>
  </CourseGoals>
  <CourseGoals>
    <template #default="goalsProps">
      <h1 class="color-red">{{ goalsProps.item }}</h1>
      <p class="bg-green">Desc: {{ goalsProps.itemDesc }}</p>
    </template>
  </CourseGoals>
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
import BadgeList from "./components/BadgeList.vue";
import UserInfo from "./components/UserInfo.vue";
import CourseGoals from "./components/CourseGoals.vue";

export default {
  components: {
    //"the-header": TheHeader,
    //TheHeader: TheHeader,
    TheHeader,
    BadgeList,
    UserInfo,
    CourseGoals,
  },
  data() {
    return {
      activeUser: {
        name: "Maximilian Schwarzmüller",
        description: "Site owner and admin",
        role: "admin",
      },
    };
  },
};
</script>

<style>
html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
.color-red {
  color: red;
}
.bg-green {
  background-color: greenyellow;
}
</style>