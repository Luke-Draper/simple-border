
# Simple Border

A small pure CSS framework for positioning elements around any block level elements.

## Setup

Simply download the SimpleBorder.css file or SimpleBorder.min.css file and link it in your HTML head.

```
<link rel="stylesheet" href="SimpleBorder.min.css">
```

## Getting Started

This framework is used by surrounding the element you want to border with an unordered list and list item.
The unordered list must have the class "sb-frame" which sets up a grid around the target element.
The target element must be in a list item with the class "sb-content" which places it in the correct location in the grid.

**Basic Setup Example**
```
<p>Lorem Ipsum<p>
```
*Becomes*
```
<ul class="sb-frame">
  <li class="sb-content">
    <p>Lorem Ipsum</p>
  </li>
</ul>
```

Once that is set up you can add more list items for each of the edges, corners, and the center.
Each of the list items needs to have a positioning class in the format "sb-(position)".
Valid positions are top, bottom, left, right, center, top-left, top-right, bottom-left, and bottom-right : or abbreviated as t, b, l, r, c, tl, tr, bl, and br.
If you want to make sure that you can see your content in front of the border then put your border list items first in the list.

**Basic Example**
```
<ul class="sb-frame">
  <li class="sb-t">
    <svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg">
      <path stroke="red" fill="none" stroke-width="4" d="M 2,2 L 2,46 L 46,46 L 46,2 z"/>
    </svg>
  </li>
  <li class="sb-bl">
    <svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg">
      <path stroke="green" fill="none" stroke-width="4" d="M 2,2 L 2,46 L 46,46 L 46,2 z"/>
    </svg>
  </li>
  <li class="sb-c">
    <svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg">
      <path stroke="blue" fill="none" stroke-width="4" d="M 2,2 L 2,46 L 46,46 L 46,2 z"/>
    </svg>
  </li>
  <li class="sb-content">
    <p>Lorem Ipsum</p>
  </li>
</ul>
```

If you would like you can further customize your borders by adding alignment classes or removing an image from the flow of the page so that it can flow under the content.
Alignment is done using these classes:
* "sb-align-x-left"(sb-axl)
* "sb-align-x-center"(sb-axc)
* "sb-align-x-right"(sb-axr)
* "sb-align-y-top"(sb-ayt)
* "sb-align-y-center"(sb-ayc)
* "sb-align-y-bottom"(sb-ayb)

In order to have the image flow under your content the list element must have the sb-ignore-flow-frame(sb-iff) class applied to it as well as its position, then its content needs to be put in a div with the class sb-ignore-flow-content(sb-ifc).

It is worth noting that when using the ignore flow classes your content is completely removed from the flow of the page. As such if you use a top left corner image ignoring flow thenit will align to the top left corner of the content.
This can be remedied by adding an extra list item in the same location with a class forcing a certain minimum width and height.

**Example**
```
<ul class="sb-frame">
  <li class="sb-t sb-axl">
    <svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg">
      <path stroke="red" fill="none" stroke-width="4" d="M 2,2 L 2,46 L 46,46 L 46,2 z"/>
    </svg>
  </li>
  <li class="sb-bl sb-iff">
    <div class="sb-ifc">
      <svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg">
        <path stroke="green" fill="none" stroke-width="4" d="M 2,2 L 2,46 L 46,46 L 46,2 z"/>
      </svg>
    </div>
  </li>
  <li class="sb-bl" style="min-width: 48px; min-height: 48px;"></li>
  <li class="sb-c sb-axr sb-ayb">
    <svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg">
      <path stroke="blue" fill="none" stroke-width="4" d="M 2,2 L 2,46 L 46,46 L 46,2 z"/>
    </svg>
  </li>
  <li class="sb-content">
    <p>Lorem Ipsum</p>
  </li>
</ul>
```

To see a simple example of this framework in action please visit [CodePen](https://codepen.io/luke-draper/pen/drwoYE)

## Authors

* **Luke Draper** - *Initial work* - [Luke-Draper](https://github.com/Luke-Draper)

## License

This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for details
