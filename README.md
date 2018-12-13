Canvas API Example

This is a short demo of the canvas API and a few of it's features. The canvas API is a browser API that is default for most web browsers. It allows the user to create an area where they can modify pictures or add drawings.

You can create a canvas, then draw a variety of shapes or add an image. For example:

```
ctx = document.getElementById('canvas').getContext('2d');
img.src = 'https://upload.wikimedia.org/wikipedia/commons/thumb/e/ec/Mona_Lisa%2C_by_Leonardo_da_Vinci%2C_from_C2RMF_retouched.jpg/687px-Mona_Lisa%2C_by_Leonardo_da_Vinci%2C_from_C2RMF_retouched.jpg';
img.onload = function() {
    ctx.drawImage(img, 0, 0);
};
```

This will create a canvas using the `img`, which is a link to the Mona Lisa.

Another feature is drawing lines on the canvas.

```
ctx.beginPath();
ctx.moveTo(264, 300);
ctx.lineTo(304, 310);
ctx.lineTo(344, 300);
ctx.stroke();
```

The `beginPath()` and `movePath(x,y)` will create a start point at the given coordinates. Then `lineTo(x,y)` will create a line to the given coordinates. Finally, `stroke()` will draw the lines.

The last feature I added was a clear button feature.

```clear.addEventListener("click", function() {
    ctx.setTransform(1, 0, 0, 1, 0, 0);
    ctx.clearRect(0, 0, ctx.canvas.width, ctx.canvas.height);
    ctx.drawImage(img, 0, 0);
})
```

When clicking the button designated `clear` in the javascript file, it will clear the canvas, then redraw the initial image.

Canvas is useful in any circumstance when you want to draw an image in the browser, and want to modify or transform the image.

To run the demo, download both files, ensure both are in the same folder, then open the `index.html`
