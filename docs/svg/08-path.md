# Drawing A Paths with SVG
Up until now, the SVG examples we were showing you were all pretty simple.  They were
not very different from the Turtle Graphics drawings that we generated in Scratch or
with our turtle graphics libraries in Python.  But now we will start to really
show how the SVG standard is really impressive.  And this is where SVG paths come in.
In SVG, the path operator is considered the most powerful tool in our drawing library!

The ```d``` attribute is the way that that we pass our drawing data to the path element.
But  ```d``` is really, really smart.  It knows how to move to any point in our drawing
area and then use relative horizontal and vertical drawing commands from that initial moveto point.

Here are the three initial "commands that we will use:

1. M - move to any X,Y point
2. H - move Horizontally
3. V - move Vertically
4. L - draw a line to a given point (Lineto)

## Simple Paths with Move, Horizontal, Vertical and Lineto Commands

Here is the path element used to draw a simple square
```html
<svg width="100" height="100">
  <path d="M 10,10 H 90 V 90 H 10 L 10,10"
      fill="none" stroke="blue" stroke-width="3"/>
</svg>
```

<svg width="100" height="100">
  <path d="M 10,10 H 90 V 90 H 10 L 10,10"
     fill="none" stroke="blue" stroke-width="3"/>
</svg>

## Closing Your Path With "Z"
Sometimes you don't want to put in that last Lineto command.  You can just use the letter "z" to tell it where to go back to the starting point.

```html
<svg width="100" height="100">
  <path d="M 10,10 H 90 V 90 H 10 Z"
     fill="none" stroke="blue" stroke-width="3"/>
</svg>
```

## Curve commands
Now that you have the basics of path commands drawing straight lines, lets have some fun with drawing curves.  You can always draw curves with lots and lots of small short lines.  But it is very inefficient to send thousands of little drawing commands to the web browser.  What if we could just tell
the web browser to draw a graceful curve between points?  That is where the SVG Path Curve command comes in handy.

* C - Draw a Cubic Bézier curve using x1 y1, x2 y2 and x y

Here is the SVG code that draws a curve from (10,10) through 100,100 and ends at (200, 10).

```html
<svg width="100" height="100">
   <path d="M 10,10 C 20,20 100,100 200,10" 
   stroke="black" fill="transparent"/>
</svg>
```
Here is what it looks like:

<svg width="200" height="100">
   <path d="M 10,10 C 20,20 100,100 200,10" 
   stroke="black" fill="transparent" stroke-width="3"/>
</svg>

Note that there are a few differences.  We don't just add the center point of the curve.
We also tell the direction to proceed from the origin (in a diagonal line from 10,10 to 20,20) is one additional point.  The center point of the curve is 100,100 and the final point is 200,10

## Sawtooth vs Sine Wave
A sawtooth wave is a wave that has straight lines that go from a minimum to a maximum.
```html
<svg width="700" height="110">
   <path d="M 0,0 L 100,100 L 200,0 L 300,100 L 400,0 L 500,100 L 600,0 L 700,100 L 800,0" 
   stroke="black" fill="none" stroke-width="3"/>
   <!-- This is the axis line -->
   <path d="M 0,50 L 700,50" fill="none" stroke="silver" stroke-width="1">
</svg>
```

<svg width="700" height="110">
   <path d="M 0,0 L 100,100 L 200,0 L 300,100 L 400,0 L 500,100 L 600,0 L 700,100 L 800,0" 
   stroke="black" fill="none" stroke-width="3"/>
    <path d="M 0,50 L 700,50" fill="none" stroke="silver" stroke-width="1">
</svg>

<svg width="700" height="110">
   <path d="M 0,0 C 50,0 25,25 50,50 C 50,100 150,50 200,0" 
   stroke="black" fill="none" stroke-width="3"/>
</svg>

<svg width = "150px" height = "200px" viewBox = "0 0 100 100">
         <path stroke = "black" fill = "none" d = "M0,0 C36.42,0 70.58,100 100,100" />
</svg>