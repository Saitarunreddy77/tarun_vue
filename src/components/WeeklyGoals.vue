<template>
  <div class="container">
    <div class="logo">
        <img src="https://static.vecteezy.com/system/resources/previews/021/425/348/non_2x/a-logo-for-a-health-and-fitness-company-free-vector.jpg" alt="Company Logo">
    </div>
    <h1>Weekly Fitness Goals</h1>
</div>

    <div class="weekly-goals">
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
  .container {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
}

.logo {
    max-width: 70px; 
    text-align: center;
}

.logo img {
    width: 100%;
}

h1 {
    font-size: 24px;
    margin-top: 10px; 
}

  
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
  
