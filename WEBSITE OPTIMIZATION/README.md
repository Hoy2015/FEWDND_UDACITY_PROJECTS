# Udacity Website Optimization
This project aims to optimize the example website provided to achieve a target Google PageSpeed score and to make the site contained in ```views``` run at 60fps.

## Installation

Clone this repo:
```
git clone https://github.com/Hoy2015/WEBSITE OPTIMIZATION.git
```
Run the index file:
```
open index.html
```

## Optimization of the web page

- Minification & concatenatenation of `HTML` `CSS` `JS` files.
- Smaller Images.
- JS files include the `async` tag.
- Inlining of `CSS and JS` to save requests.
- Included media queries in `CSS`.


### Running at 60 fps
- A modified `updatePositions` function is included to avoid requesting a new layout for each element:

```
function updatePositions() {
  frame++;
  window.performance.mark("mark_start_frame");

  var items = document.querySelectorAll('mover');
  var const_theta = document.body.scrollTop / 1250;
  for (var i = 0; i < items.length; i++) {
    var phase = Math.sin(const_theta + (i % 5));
    items[i].style.left = items[i].basicLeft + 100 * phase + 'px';
  }
```

- requestAnimationFrame now wraps `updatePositions` as necessary.
- Replacement of  `querySelector, querySelectorAll` calls to `getElementByID`
or `getElementsByClassName` as needed.

- Refactoring of `changePizzaSizes`.
- Use of `sizeSwitcher`.

- The number of pizzas in set to **30** in the `DOMContentLoaded` event.

- Removal of width & height changes from `DOMContentLoaded` listener
- Some paints are avoided with CSS.
 
