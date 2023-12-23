# web-study

### Bezier Curve using D3js

```js
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Curve with D3.js</title>
  <script src="https://d3js.org/d3.v6.min.js"></script>
</head>
<body>

<script>
  // Set up the SVG container
  const svgWidth = 400;
  const svgHeight = 200;

  const svg = d3.select("body").append("svg")
    .attr("width", svgWidth)
    .attr("height", svgHeight);

  // Define the data for the curve
  const curveData = [
    { x: 50, y: 100 },
    { x: 200, y: 50 },
    { x: 260, y: 90 },
    { x: 350, y: 100 }
  ];

  // Create the line generator with a curve
  const lineGenerator = d3.line()
    .x(d => d.x)
    .y(d => d.y)
    .curve(d3.curveCardinal);

  // Append a path element to the SVG and set its attributes
  svg.append("path")
    .data([curveData])
    .attr("d", lineGenerator)
    .attr("stroke", "RGB(240,0,10)")
    .attr("stroke-width", 5)
    .attr("fill", "none")
    .attr("stroke-dasharray", "5, 2");

</script>

</body>
</html>
```

### draw dashed line using D3js

```js
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Dotted Line with D3.js</title>
  <script src="https://d3js.org/d3.v6.min.js"></script>
</head>

<body>

  <script>
    
    // Set up the SVG container
    const svgWidth = 400;
    const svgHeight = 200;

    const svg = d3.select("body").append("svg")
      .attr("width", svgWidth)
      .attr("height", svgHeight);

    // Define the data for the line
    const lineData = [
      { x: 50, y: 100 },
      { x: 200, y: 50 },
      { x: 350, y: 100 }
    ];

    // Create the line generator
    const lineGenerator = d3.line()
      .x(d => d.x)
      .y(d => d.y);

    // Append a path element to the SVG and set its attributes
    svg.append("path")
      .data([lineData])
      .attr("d", lineGenerator)
      .attr("stroke", "black")
      .attr("stroke-width", 2)
      .attr("fill", "none")
      .attr("stroke-dasharray", "5, 8"); // Set the dash pattern

  </script>

</body>

</html>
```
