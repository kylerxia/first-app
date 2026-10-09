
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My First App</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f3f0ff;
      padding: 30px 16px;
      text-align: center;
    }
    .app {
      max-width: 420px;
      margin: auto;
      background: white;
      padding: 24px;
      border-radius: 16px;
    }
    input, button {
      padding: 12px;
      margin: 5px 0;
      border-radius: 8px;
      border: 1px solid #ccc;
    }
    button {
      cursor: pointer;
      background: #7056d8;
      color: white;
      border: none;
    }
    li {
      text-align: left;
      padding: 8px;
      overflow-wrap: anywhere;
    }
    li.done {
      text-decoration: line-through;
      color: gray;
    }
  </style>
</head>
<body>
  <div class="app">
    <h1>My To-Do List ✨</h1>
    <p>What do you need to do today?</p>

    <form id="taskForm">
      <input id="taskInput"
        placeholder="Enter a task..." required>
      <button type="submit">Add</button>
    </form>

    <ul id="taskList"></ul>
  </div>

  <script>
    const form = document.getElementById("taskForm");
    const input = document.getElementById("taskInput");
    const list = document.getElementById("taskList");

    form.addEventListener("submit", function(event) {
      event.preventDefault();

      const task = input.value.trim();
      if (!task) return;

      const item = document.createElement("li");
      item.textContent = task;
      item.title = "Click to mark complete";

      item.addEventListener("click", function() {
        item.classList.toggle("done");
      });

      list.appendChild(item);
      input.value = "";
    });
  </script>
</body>
</html>
