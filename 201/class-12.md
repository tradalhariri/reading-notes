# Drawing shapes with canvas 

* In this article you will learn how to draw rectangles, triangles, lines, arcs and curves in canvas.
* Drawing rectangles : there are three functions to draw rectangle on canvas
  1. fillRect(x, y, width, height) => Draws a filled rectangle.
  2. strokeRect(x, y, width, height) => Draws a rectangular outline.
  3. clearRect(x, y, width, height) => Clears the specified rectangular area, making it fully transparent.

  ```js
  function draw() {
    var canvas = document.getElementById('canvas');
    if (canvas.getContext) {
      var ctx = canvas.getContext('2d');
  
      ctx.fillRect(25, 25, 100, 100);
      ctx.clearRect(45, 45, 60, 60);
      ctx.strokeRect(50, 50, 50, 50);
    }
  }

  draw();
  ```
  ![Rectangle](https://i.ibb.co/ZdzsG5S/Screenshot-18.png)
* Drawing paths : a path is a list of points connected by segments of lines to make a shap.
  1. Drawing a triangle using bath - first we need to start a path by calling `beginPath()` method to reset the list of the path. then we choose the starting point by calling `moveTo(x,y)` method and then set of calling to the methode `lineTo(x,y)` then we need either fill or stroke the triangle for example.
    ```js
    function draw() {
        var canvas = document.getElementById('canvas');
        if (canvas.getContext) {
        var ctx = canvas.getContext('2d');
    
        ctx.beginPath();
        ctx.moveTo(50, 50);
        ctx.lineTo(100, 75);
        ctx.lineTo(100, 25);
        ctx.fill();
        }
    }

    draw();
    ```
    ![triangle](https://i.ibb.co/3sBBZds/Screenshot-19.png)
  2. Arcs : To draw arcs or circles, we use the `arc()` or `arcTo()` methods.
     1. `arc(x, y, radius, startAngle, endAngle, counterclockwise)` Draws an arc which is centered at (x, y) position with radius r starting at startAngle and ending at endAngle going in the given direction indicated by counterclockwise (defaulting to clockwise).
     2. `arcTo(x1, y1, x2, y2, radius)` Draws an arc with the given control points and radius, connected to the previous point by a straight line.
     
        ```js
        function draw() {
        var canvas = document.getElementById('canvas');
        if (canvas.getContext) {
        var ctx = canvas.getContext('2d');
    
        for (var i = 0; i < 4; i++) {
            for (var j = 0; j < 3; j++) {
            ctx.beginPath();
            var x = 25 + j * 50; // x coordinate
            var y = 25 + i * 50; // y coordinate
            var radius = 20; // Arc radius
            var startAngle = 0; // Starting point on circle
            var endAngle = Math.PI + (Math.PI * j) / 2; // End point on circle
            var counterclockwise = i % 2 !== 0; // clockwise or counterclockwise
    
            ctx.arc(x, y, radius, startAngle, endAngle, counterclockwise);
    
            if (i > 1) {
                ctx.fill();
            } else {
                ctx.stroke();
            }
            }
           }
          }
         }
        draw();
         ```

![Arc](https://i.ibb.co/68M0Bh3/Screenshot-20.png)

# Applying styles and colors to canvas 

* colors : if you want to add  a color to a shape there are two properties you can use 
  1. `fillStyle = color` in the following example we create 36 rectangles each has a width and height of 25 and fill each of them by different color.

    ```js
    function draw() {
        var ctx = document.getElementById('canvas').getContext('2d');
        for (var i = 0; i < 6; i++) {
        for (var j = 0; j < 6; j++) {
            ctx.fillStyle = 'rgb(' + Math.floor(255 - 42.5 * i) + ', ' +
                            Math.floor(255 - 42.5 * j) + ', 0)';
            ctx.fillRect(j * 25, i * 25, 25, 25);
        }
        }
    }


    draw();
   ```

![coloredRec](https://i.ibb.co/Dfmkbj4/Screenshot-21.png)

  2. `strokeStyle = color` 
  in the following example we will create 36 small circles and color the the border of each by different color

  ```js
  function draw() {
    var ctx = document.getElementById('canvas').getContext('2d');
    for (var i = 0; i < 6; i++) {
      for (var j = 0; j < 6; j++) {
        ctx.strokeStyle = 'rgb(0, ' + Math.floor(255 - 42.5 * i) + ', ' +
                         Math.floor(255 - 42.5 * j) + ')';
        ctx.beginPath();
        ctx.arc(12.5 + j * 25, 12.5 + i * 25, 10, 0, Math.PI * 2, true);
        ctx.stroke();
      }
    }
  }

  draw();
  ```

![coloredCircle](https://i.ibb.co/ZSt39ry/Screenshot-22.png)
* Transparency : we can apply transparency by setting global alpha transparency value  or by setting transparencey value for strok or fill.

* Line styles 
  1. we can set the width of the line by using the property `lineWidth = value` 
  2. we can set the the lineCap to one of three values `butt, round and square` which change the appearing of the end of the line.
* Gradients : 
     1. `createLinearGradient(x1, y1, x2, y2)` create a linear gradient starting from ponint `x1,y1` and ending in point `x2,y2
     2. `createRadialGradient(x1, y1, r1, x2, y2, r2)` create radial gradient and the parameters represent two circles the first is centered at `x1,y1 and radius of r1` and the second is centered at `x2,y2 and radius of r2` 


# Drawing text 

 * we can draw a text using two methods 
   1. `fillText(text, x, y [, maxWidth])`  you can using this method to fill the given text at given point with optional maximum width.
   2. `strokeText(text, x, y [, maxWidth])` you can using this method to stroke the given text at given point with optional maximum width.


# Easily Create animated Charts using Chart.js 

* charts is better than tables to presents the data because it conveys the data quickly . Chart.js is javascript plugin which uses canvas element to draw amazing charts like line , bar and pie charts. we can either download this plugin or copy paste the cdn link.
  1. line chart : to create a line chart we first need to access the canvas tag on the html page and then we call an opject of the Chart and passing parameters. the first is the canvas element and the second is a javascript object which contains the type of chart and the data
   
   ```js
   let buyers = document.getElementById('buyers').getContext('2d');

  const labels = [
    'January',
    'February',
    'March',
    'April',
    'May',
    'June',
  ];
  const data = {
    labels: labels,
    datasets: [{
      label: 'My First dataset',
      fillColor : "rgba(172,194,132,0.4)",
			strokeColor : "#ffffff",
			pointColor : "#fff000",
			pointStrokeColor : "#ff00ff",
      backgroundColor: 'rgb(255, 99, 132)',
      borderColor: 'rgb(255, 99, 132)',
      data: [0, 10, 5, 2, 20, 30, 45],
    }]
  };


  const config = {
    type: 'line',
    data:data,
    options: {}
  };


    let myChart = new Chart(
        buyers,
        config
    );

  ```

  ![linechart](https://i.ibb.co/rQYCpn5/Screenshot-23.png)


  2. the following is the same example but making it a bar chart 

  ```js 
        let buyers = document.getElementById('buyers').getContext('2d');

        const labels = [
        'January',
        'February',
        'March',
        'April',
        'May',
        'June',
        ];

        const data = {
        labels: labels,
        datasets: [{
            label: 'My First Dataset',
            data: [65, 59, 80, 81, 56, 55, 40],
            backgroundColor: [
            'rgba(255, 99, 132, 0.2)',
            'rgba(255, 159, 64, 0.2)',
            'rgba(255, 205, 86, 0.2)',
            'rgba(75, 192, 192, 0.2)',
            'rgba(54, 162, 235, 0.2)',
            'rgba(153, 102, 255, 0.2)',
            'rgba(201, 203, 207, 0.2)'
            ],
            borderColor: [
            'rgb(255, 99, 132)'],
        }],
        };

        const config = {
        type: 'bar',
        data: data,
        options: {
            scales: {
            y: {
                beginAtZero: true
            }
            }
        },
        };

        let myChart = new Chart(
        buyers,
        config
        );
   ```

   ![barchart](https://i.ibb.co/m5sxPrw/Screenshot-24.png)
   