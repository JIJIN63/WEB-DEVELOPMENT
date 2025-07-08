# WEB-DEVELOPMENT
# WEB DEVELOPMENT PROJECT
 # TASK-1 Create an interactive navigation menu that changes color or style when scrolled or when hovering over a menu item.


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsive Landing Page</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <nav id="navbar">
        <div class="logo">Logo</div>
        <ul class="nav-links">
            <li><a href="#">Home</a></li>
            <li><a href="#">About</a></li>
            <li><a href="#">Contact</a></li>
        </ul>
    </nav>
    <div class="content">
        <!-- Your page content here -->
        <h1>Welcome to our website</h1>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed sit amet nulla auctor, vestibulum magna sed, convallis ex.</p>
    </div>

    <script src="script.js"></script>
</body>
</html>

OUTPUT:

Logo
[Home]
[About]
[Contact]
Welcome to our website
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed sit amet nulla auctor, vestibulum magna sed, convallis ex.


# TASK-2 CALCULATOR WEB APPLICATION

# Build a fully functional calculator to practice DOM manipulation, event handling, and basic arithmetic operations.
# Implement functions to handle input parsing, event listeners on equal button, error handling, keyboard input handling.

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Calculator</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <div class="calculator">
    <input type="text" id="display" disabled />
    <div class="buttons">
      <button class="btn" data-key="C">C</button>
      <button class="btn" data-key="⌫">⌫</button>
      <button class="btn" data-key="/">/</button>
      <button class="btn" data-key="*">*</button>

      <button class="btn" data-key="7">7</button>
      <button class="btn" data-key="8">8</button>
      <button class="btn" data-key="9">9</button>
      <button class="btn" data-key="-">-</button>

      <button class="btn" data-key="4">4</button>
      <button class="btn" data-key="5">5</button>
      <button class="btn" data-key="6">6</button>
      <button class="btn" data-key="+">+</button>

      <button class="btn" data-key="1">1</button>
      <button class="btn" data-key="2">2</button>
      <button class="btn" data-key="3">3</button>
      <button class="btn equal" data-key="=">=</button>

      <button class="btn" data-key="0">0</button>
      <button class="btn" data-key=".">.</button>
    </div>
  </div>

  <script src="main.js"></script>
</body>
</html>

OUTPUT:

C ⌫ / * 7 8 9 - 4 5 6 + 1 2 3 = 0 .

# TASK 3 QUIZ GAME APPLICATION

# Develop an interactive multiple-choice quiz game that displays questions, collects answers, and provides a score at the end.


const quizData = [
    {
    question: "What is the capital of France?",
        type: "single-select",
        options: ["Paris", "London", "Berlin", "Rome"],
        answer: "Paris"
    },
    {
    question: "What are the colors of the French flag?",
        type: "multi-select",
        options: ["Red", "White", "Blue", "Green"],
        answer: ["Red", "White", "Blue"]
    },
    {
    question: "The largest planet in our solar system is _______.",
        type: "fill-in-the-blank",
        answer: "Jupiter"
    }, // Add more questions...
];
let currentQuestion = 0;let score = 0;
const questionElement = document.getElementById("question");
const optionsElement = document.getElementById("options");
const fillInTheBlankElement = document.getElementById("fill-in-the-blank");
const submitButton = document.getElementById("submit");
const nextButton = document.getElementById("next");
const resultElement = document.getElementById("result");
const scoreElement = document.getElementById("score");
function loadQuestion() {
    const question = quizData[currentQuestion];
    questionElement.textContent = question.question;
    optionsElement.innerHTML = "";
    fillInTheBlankElement.style.display = "none";
 if (question.type === "single-select" || question.type === "multi-select") {
        question.options.forEach(option => {
            const label = document.createElement("label");
            const input = document.createElement("input");
            input.type = question.type === "single-select" ? "radio" : "checkbox";
            input.name = "option";
            input.value = option;
            label.appendChild(input);
            label.appendChild(document.createTextNode(option));
            optionsElement.appendChild(label);
        });
    } else if (question.type === "fill-in-the-blank") {
        fillInTheBlankElement.style.display = "block";
        }
}
function checkAnswer() {
    const question = quizData[currentQuestion];

    if (question.type === "single-select") {
        const selectedOption = document.querySelector('input[name="option"]:checked');
        if (selectedOption && selectedOption.value === question.answer) {
            score++;
            resultElement.textContent = "Correct!";
        } else {
            resultElement.textContent = `Incorrect! The correct answer is ${question.answer}.`;
        }
    } else if (question.type === "multi-select") {
        const selectedOptions = Array.from(document.querySelectorAll('input[name="option"]:checked')).map(option => option.value);
        if (JSON.stringify(selectedOptions.sort()) === JSON.stringify(question.answer.sort())) {
            score++;
            resultElement.textContent = "Correct!";
        } else {
            resultElement.textContent = `Incorrect! The correct answers are ${question.answer.join(', ')}.`;
        }
    } else if (question.type === "fill-in-the-blank") {
        if (fillInTheBlankElement.value.trim().toLowerCase() === question.answer.toLowerCase()) {
            score++;
            resultElement.textContent = "Correct!";
        } else {
            resultElement.textContent = `Incorrect! The correct answer is ${question.answer}.`;
            }
    }
 scoreElement.textContent = `Score: ${score} / ${currentQuestion + 1}`;
}
function nextQuestion() {
    currentQuestion++;
    if (currentQuestion >= quizData.length) {
        questionElement.textContent = "Quiz finished!";
        optionsElement.innerHTML = "";
        fillInTheBlankElement.style.display = "none";
        submitButton.style.display = "none";
        nextButton.style.display = "none";
        resultElement.textContent = `Your final score is ${score} out of ${quizData.length}.`;
    } else {
        loadQuestion();
        resultElement.textContent = "";    }
}
loadQuestion();
submitButton.addEventListener("click", checkAnswer);
nextButton.addEventListener("click", nextQuestion);

OUTPUT:

Initial Load
- Question: What is the capital of France?
- Options: Paris, London, Berlin, Rome
- Score: 0 / 0

After Submitting Answer
- Result: Correct! or Incorrect! The correct answer is Paris.
- Score: 1 / 1 (if correct)

After Completing Quiz
- Quiz finished!
- Your final score is X out of Y.


# TASK-4 TO-DO WEB APP

# Develop a basic to-do app that enables a user to add maintain tasks.
# Allow users to add/organize items in lists. Mark them Completed, Edit them, Set Date & Time of tasks
 
JavaScript (in script.js file)
let tasks = [];

const taskInput = document.getElementById('task-input');
const taskDate = document.getElementById('task-date');
const addTaskBtn = document.getElementById('add-task-btn');
const taskList = document.getElementById('task-list');

addTaskBtn.addEventListener('click', addTask);

function addTask() {
    const taskText = taskInput.value;
    const taskDateTime = taskDate.value;
    if (taskText !== '') {
        const task = {
            text: taskText,
            date: taskDateTime,
            completed: false
        };
        tasks.push(task);
        renderTaskList();
        taskInput.value = '';
        taskDate.value = '';
    }
}

function renderTaskList() {
    taskList.innerHTML = '';
    tasks.forEach((task, index) => {
        const taskElement = document.createElement('li');
        taskElement.classList.add('task');
        if (task.completed) {
            taskElement.classList.add('completed');
        }
        taskElement.innerHTML = `
            ${task.text} - ${task.date}
            <div class="actions">
                <button class="complete-btn">Complete</button>
                <button class="edit-btn">Edit</button>
                <button class="delete-btn">Delete</button>
            </div>
        `;
        taskElement.querySelector('.complete-btn').addEventListener('click', () => {
            task.completed = !task.completed;
            renderTaskList();
        });
        taskElement.querySelector('.edit-btn').addEventListener('click', () => {
            const newText = prompt('Enter new task text:', task.text);
            const newDate = prompt('Enter new task date and time:', task.date);
            if (newText !== null && newDate !== null) {
                task.text = newText;
                task.date = newDate;
                renderTaskList();
            }
        });
        taskElement.querySelector('.delete-btn').addEventListener('click', () => {
            tasks.splice(index, 1);
            renderTaskList();
        });
        taskList.appendChild(taskElement);
    });
}

OUTPUT:
Initial Load
- To-Do List page with input field for task text, date and time field, and "Add Task" button
- Empty task list

After Adding Task
- Task list displays the added task with text, date, and time
- Task list item has "Complete", "Edit", and "Delete" buttons

After Marking Task as Completed
- Task list item is displayed with strikethrough text
- Task is marked as completed

After Editing Task
- Task list item is updated with new text and date/time

After Deleting Task
- Task list item is removed from the list


