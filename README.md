# Bharat_Intern
#App development 

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>YourTo-Do List</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f5f5f5; /* Light pastel background color */
    }
    .container {
      max-width: 600px;
      margin: 20px auto;
      background-color: #ffffff; /* Light pastel container background color */
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }
    h1 {
      text-align: center;
      color: #ff7eb9; /* Pastel pink heading color */
    }
    #taskInput {
      width: 100%;
      padding: 10px;
      margin-bottom: 10px;
      border: 1px solid #e0e0e0; /* Light pastel border color */
      border-radius: 5px;
      box-sizing: border-box;
    }
    .taskItem {
      background-color: #fff3e6; /* Light pastel task item background color */
      margin-bottom: 10px;
      padding: 10px;
      border-radius: 5px;
    }
    .btn {
      padding: 10px 20px;
      border: none;
      background-color: #a7e9af; /* Light pastel button background color */
      color: #555; /* Pastel button text color */
      cursor: pointer;
      border-radius: 5px;
    }
    .btn:hover {
      background-color: #86cf96; /* Light pastel button background color on hover */
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Your To-Do List !</h1>
    <input type="text" id="taskInput" placeholder="Add a new task...">
    <button onclick="addTask()" class="btn">Add Task</button>
    <div id="taskList"></div>
  </div>

  <script>
    function addTask() {
      var taskInput = document.getElementById('taskInput');
      var taskList = document.getElementById('taskList');
      var newTask = document.createElement('div');
      newTask.className = 'taskItem';
      newTask.textContent = taskInput.value;
      taskList.appendChild(newTask);
      taskInput.value = '';
      newTask.onclick = function() {
        this.remove();
      }
    }
  </script>
</body>
</html>
