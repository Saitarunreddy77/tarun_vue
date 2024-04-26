<template>
    <div class="weekly-goals">
      <h1>Weekly Fitness Goals</h1>
      <div v-for="(dayData, day) in weeklyData" :key="day">
        <div class="day-data">
          <h2>{{ day }}</h2>
          <p>Activity Goal: {{ dayData.activity_goal }}</p>
          <p>Daily Goal: {{ dayData.daily_goal }}</p>
          <p>Steps: {{ dayData.steps }}</p>
          <p>Distance: {{ dayData.distance }}</p>
          <p>Sleep: {{ dayData.sleep }}</p>
          <p>Energy Consumption: {{ dayData.energy_consumption }}</p>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'WeeklyGoals',
    props: {
      weeklyData: Object
    }
  };
  </script>
  
  <style scoped>
  
  .weekly-goals {
    flex: 1;
    padding: 20px;
    background-color: #f0f0f0;
  }

  .weekly-goals h1 {
  margin-bottom: 20px;
  text-align: center;
}
  
  .day-data {
    margin-bottom: 20px;
    padding: 20px;
    border: 1px solid #ccc;
    background-color: #fff;
  }
  </style>
  