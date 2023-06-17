# Ferrocementcanal
<!DOCTYPE html>
<html>
<head>
<title>Ferrocement Canal Lining Video Animation</title>
<style>
body {
  background-color: black;
}

canvas {
  width: 500px;
  height: 500px;
}
</style>
</head>
<body>
<canvas id="canvas"></canvas>
<script>
var ctx = document.getElementById("canvas").getContext("2d");

// Create a list of ferrocement canal linings
var canalLinings = [];

// Create a loop to create the ferrocement canal linings
for (var i = 0; i < 10; i++) {

  // Create a new ferrocement canal lining
  var canalLining = {
    x: Math.random() * canvas.width,
    y: Math.random() * canvas.height,
    width: 100,
    height: 100,
    color: "red"
  };

  // Add the ferrocement canal lining to the list
  canalLinings.push(canalLining);
}

// Create a loop to animate the ferrocement canal linings
function animate() {

  // Clear the canvas
  ctx.clearRect(0, 0, canvas.width, canvas.height);

  // Update the position of the ferrocement canal linings
  for (var i = 0; i < canalLinings.length; i++) {

    // Move the ferrocement canal lining down
    canalLinings[i].y += 1;

    // If the ferrocement canal lining has reached the bottom of the canvas, remove it from the list
    if (canalLinings[i].y >= canvas.height) {
      canalLinings.splice(i, 1);
    }
  }

  // Draw the ferrocement canal linings
  for (var i = 0; i < canalLinings.length; i++) {

    // Draw the ferrocement canal lining
    ctx.fillStyle = canalLinings[i].color;
    ctx.fillRect(canalLinings[i].x, canalLinings[i].y, canalLinings[i].width, canalLinings[i].height);
  }

  // Request a new animation frame
  requestAnimationFrame(animate);
}

// Start the animation
animate();
</script>
</body>
</html>
