<template>
  <div>
    <TheHeader />
    <button @click="setSelectedComponent('ActiveGoals')">Active goals</button>
    <button @click="setSelectedComponent('MangeGoals')">Mange goals</button>
    <!-- <ActiveGoals v-if="selectedComponent ==='ActiveGoals' " />
    <MangeGoals v-else/> -->
    <keep-alive>
      <component :is="selectedComponent" />
    </keep-alive>
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue';
import ActiveGoals from './components/ActiveGoal.vue';
import MangeGoals from './components/MangeGoals.vue';
// import BadgeList from './components/BadgeList.vue';
// import UserInfo from './components/UserInfo.vue';
// import CourseGoals from './components/CourseGoals.vue';

export default {
  components: {
    TheHeader,
    ActiveGoals,
    MangeGoals,
    // BadgeList,
    // UserInfo,
    // CourseGoals,
  },
  data() {
    return {
      selectedComponent: 'ActiveGoals',
      activeUser: {
        name: 'Maximilian Schwarzmüller',
        description: 'Site owner and admin',
        role: 'admin',
      },
    };
  },
  methods: {
    setSelectedComponent(cmp) {
      this.selectedComponent = cmp;
    },
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
</style>
