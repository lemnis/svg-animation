# Stroke-dashoffset + stroke-dasharray

## Resources

* https://css-tricks.com/svg-line-animation-works/

## Variations

### Handwriting animation

1. Place some text on your favorite vector program.
2. Trace the text with the pen tool (multiple paths or one unbroken path).
3. Adjust the stroke width till the path fully covers the text.
4. Flatten the text to shapes.
5. Export the whole document.
    * Optionally optimize the text to combine the shape.
6. Open the `svg` file.
7. Wrap the text path into a `<clipPath>`.
8. Create a stylesheet or style block.
9. Add:
    ```css
    @keyframes dash {
      to {
        stroke-dashoffset: 0;
      }
    }
    ```
10. For every path:
    1. Measure the length of the path with `.getTotalLength()`
    2. Add:
    ```css
    element-name {
  	  stroke-dasharray: totalLength;
	    stroke-dashoffset: totalLength + .1; // Add .1 to prevent seeing a small part within firefox and edge
  	  animation: dash desiredDuration linear forwards;
    }
    ```
 
#### Reference
* https://youtu.be/wab7lQKHXL4
* https://codepen.io/lemnis/pen/XqodLL
