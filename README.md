# Enraged1.github.io

let timerStart;
let elapsedSeconds = 0;   // Variable to store elapsed seconds
let timerActive = true;    // Flag to track if the timer is active

function setup() {
  createCanvas(400, 200);  // Create a canvas
  textSize(32);  // Set the text size
  textAlign(CENTER, CENTER);  // Center the text
  timerStart = millis();  // Record the start time
}

function draw() {
  background(0);  // Clear the screen with a black background

  if (timerActive) {
    // Calculate elapsed time
    let currentMillis = millis();  // Get the current time in milliseconds
    elapsedSeconds = Math.floor((currentMillis - timerStart) / 1000);  // Convert to seconds
    
    // Display the elapsed time
    fill(255);
    text("Time: " + elapsedSeconds + "s", width / 2, height / 2 - 40);
    
    // Stop the timer when it reaches 20 seconds
    if (elapsedSeconds >= 20) {
      timerActive = false;
      text("Timer Stopped", width / 2, height / 2 + 40);
    }
  }
}
