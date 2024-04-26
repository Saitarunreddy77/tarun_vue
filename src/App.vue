<template>
  <div id="app">
    <WeeklyGoals :weeklyData="weeklyData" />
    <ContactInfo></ContactInfo>
    <AppFooter />
  </div>
</template>

<script>
import WeeklyGoals from './components/WeeklyGoals.vue';
import AppFooter from './components/AppFooter.vue';
import ContactInfo from './components/ContactInfo.vue';

export default {
  name: 'App',
  components: {
    WeeklyGoals,
    AppFooter,
    ContactInfo
  },
  data() {
    return {
      weeklyData: {}
    };
  },
  async created() {
    try {
      const response = await fetch('https://tarun-node.onrender.com/api');
      if (!response.ok) {
        throw new Error('Failed to fetch data');
      }
      const data = await response.json();
      if (data && data.length > 0) {
        this.weeklyData = data[0].weekly_goals;
      }
    } catch (error) {
      console.error('Error fetching data:', error);
    }
  }
};
</script>

<style>

#app {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

</style>
