# WEB-DEVELOPMENT
WEB DEVELOPMENT PROJECT
Create an interactive navigation menu that changes color or style when scrolled or when hovering over a menu item.


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


TASK-2 CALCULATOR WEB APPLICATION
Build a fully functional calculator to practice DOM manipulation, event handling, and basic arithmetic operations.
Implement functions to handle input parsing, event listeners on equal button, error handling, keyboard input handling.
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
