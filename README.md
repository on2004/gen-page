<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Random Fortune Generator</title>
  
  <!-- CSS Styling -->
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      margin-top: 50px;
    }

    input {
      padding: 8px;
      font-size: 16px;
      margin-right: 10px;
    }

    button {
      padding: 8px 12px;
      font-size: 16px;
      cursor: pointer;
    }

    #output {
      margin-top: 20px;
      font-weight: bold;
      transition: all 0.5s ease;
      font-size: 20px; /* Default font size */
      color: black;    /* Default color */
    }
  </style>
</head>
<body>
  <h1>Welcome to the Random Fortune Generator!</h1>
  <p>Enter your name to receive a fortune:</p>
  <input type="text" id="visitorName" placeholder="Your name">
  <button onclick="generate()">Get Your Fortune!</button>
  
  <p id="output"></p>

  <!-- JavaScript -->
  <script>
    // Array of random fortunes
    const fortunes = [
      "Today is your lucky day!",
      "Expect a pleasant surprise soon.",
      "Adventure awaits you around the corner.",
      "A challenge you face will soon be resolved.",
      "You will find what you are looking for.",
      "Someone from your past will bring joy into your life.",
      "Success is coming your way, stay positive."
    ];

    // Function to generate a random fortune with the visitor's name
    function generate() {
      const visitorName = document.getElementById("visitorName").value;
      if (!visitorName) {
        alert("Please enter your name!");
        return;
      }

      const randomFortune = fortunes[Math.floor(Math.random() * fortunes.length)];
      const outputElement = document.getElementById("output");

      outputElement.innerText = `${visitorName}, your fortune is: "${randomFortune}"`;
      restyle(); // Call the restyle function to apply random styles
    }

    // Function to apply random CSS styles to the output
    function restyle() {
      const outputElement = document.getElementById("output");

      // Generate random font size, color, and rotation angle
      const randomFontSize = Math.floor(Math.random() * 20) + 16 + "px";
      const randomColor = `rgb(${Math.floor(Math.random() * 256)}, ${Math.floor(Math.random() * 256)}, ${Math.floor(Math.random() * 256)})`;
      const randomRotation = `rotate(${Math.floor(Math.random() * 20) - 10}deg)`;

      // Apply the random styles to the output element
      outputElement.style.fontSize = randomFontSize;
      outputElement.style.color = randomColor;
      outputElement.style.transform = randomRotation;
    }
  </script>
</body>
</html>
