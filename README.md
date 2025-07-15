# Fitness-project
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Fitness Tracker</title>
  <style>
    body {
      font-family: sans-serif;
      background: #f5f6fa;
      margin: 0;
      padding: 0;
    }
    .container {
      max-width: 600px;
      margin: auto;
      padding: 2rem;
      background: white;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      border-radius: 10px;
      margin-top: 50px;
    }
    h1, h2 {
      text-align: center;
      color: #2f3640;
    }
    input {
      width: 100%;
      padding: 0.8rem;
      margin: 0.5rem 0;
      border: 1px solid #dcdde1;
      border-radius: 5px;
    }
    button {
      width: 100%;
      padding: 0.8rem;
      background: #44bd32;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    button:hover {
      background: #4cd137;
    }
    ul {
      list-style: none;
      padding: 0;
    }
    ul li {
      background: #dcdde1;
      margin: 0.5rem 0;
      padding: 0.5rem;
      border-radius: 5px;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>🏋️ Fitness Tracker</h1>

    <section>
      <h2>Add Workout</h2>
      <input type="text" id="workout" placeholder="Workout type (e.g., Running)" />
      <input type="number" id="duration" placeholder="Duration (minutes)" />
      <button onclick="addWorkout()">Add</button>
    </section>

    <section>
      <h2>Water Intake</h2>
      <input type="number" id="water" placeholder="Water (ml)" />
      <button onclick="addWater()">Log Water</button>
    </section>

    <section>
      <h2>Today's Summary</h2>
      <ul id="log"></ul>
    </section>
  </div>
  <script>
    const log = document.getElementById("log");

    function addWorkout() {
      const workout = document.getElementById("workout").value;
      const duration = document.getElementById("duration").value;
      if (workout && duration) {
        const calories = Math.round(duration * 5); // Estimate
        log.innerHTML += `<li>🏃‍♂️ ${workout} - ${duration} mins | 🔥 ${calories} kcal</li>`;
        document.getElementById("workout").value = "";
        document.getElementById("duration").value = "";
      }
    }

    function addWater() {
      const water = document.getElementById("water").value;
      if (water) {
        log.innerHTML += `<li>💧 Drank ${water}ml water</li>`;
        document.getElementById("water").value = "";
      }
    }
  </script>
</body>
</html>