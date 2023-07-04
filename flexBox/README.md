# flex box

[⬅ Back](../README.md)

## Intro 
This project is my REACTION to this video ⬇️

<div>
  <a href="https://www.youtube.com/watch?v=wUl3QwNjGRg"><img src="https://img.youtube.com/vi/wUl3QwNjGRg/0.jpg" alt="IMAGE ALT TEXT"></a>
</div>

## Practice 
We gonna play a small game 🐸

https://flexboxfroggy.com/

### justify-content - Whole container (n items)
💚 <b>Horizontal layout</b>

`justify-content` property defines how the browser distributes space between and around content items along the main-axis of a flex container

- flex-start: Items align to the left side of the container.
- flex-end: Items align to the right side of the container.
- center: Items align at the center of the container.
- space-between: Items display with equal spacing between them.
- space-around: Items display with equal spacing around them.

```css
#pond {
  display: flex;
  justify-content: flex-end;
}
```

### align-items - Whole container (n items)
💚 <b>Vertical layout</b>

https://developer.mozilla.org/en-US/docs/Web/CSS/align-items

- flex-start: Items align to the top of the container.
- flex-end: Items align to the bottom of the container.
- center: Items align at the vertical center of the container.
- baseline: Items display at the baseline of the container.
- stretch: Items are stretched to fit the container.

Combine those things we have (x, y)
```css
#pond {
  display: flex;
  justify-content: center;
  align-items: center;
}

```

### flex-direction - Whole container (n items)
https://developer.mozilla.org/en-US/docs/Web/CSS/flex-direction

`display:flex` by default by row which mean 3 red, green, blue if red take entire row the green will be in next row 

- row: Items are placed the same as the text direction.
- row-reverse: Items are placed opposite to the text direction.
- column: Items are placed top to bottom.
- column-reverse: Items are placed bottom to top.

🔴 The 'revese' is ONLY affect for items in single row/col 
If reverse Multiple row/col you should use `wrap-reverse`


```css
#pond {
  display: flex;
  justify-content: flex-end
}
/* BUT we want reverse the order of flex end */

#pond {
  display: flex;
  flex-direction: row-reverse;
}
```

align-items: We will entire items in one 

Given 3 items, with below styling we will have 3 item on same row at the bottom of the container 

```css
#pond {
  display: flex;
  justify-content: flex-end
}
```

With flex-directions, 3 items will sit in 3 rows 

```css
#pond {
  display: flex;
  flex-direction: column
}
```

#10 challenge
```css
#pond {
  display: flex;
  justify-content: flex-end;
  flex-direction: row-reverse;
}
```
This will move to end (flex-end) then reverse meaning will move to top (flex-start)

📒 Notice that when you set the direction to a reversed row or column, start and end are also reversed.

## 11 challenge
Notice that when the flex direction is a column, `justify-content` changes to the vertical and align-items to the horizontal.

This mean, flex-direction will reverse/swap vertical/horizontal 
===> flex-direction: is the most important ⭐️

## order - Single item 
We can choose specific order for item 

We can apply the `order` property to individual items. By default, items have a value of 0, but we can use this property to also set it to a positive or negative integer value (-2, -1, 0, 1, 2).

By default all items are 0. So if you set order = 1 or 2 greater than 0 it will move the item forward. Otherwise (-1, -2) backward

```css
#pond {
  display: flex;
}

.yellow {
  order: 1 
}
```

## align-self - Single item 

Same align-items but for single item 

```css
#pond {
  display: flex;
  align-items: flex-start;
}

.yellow {
align-self: flex-end;
order: 2
}
```

## flex-wrap - Whole container 
This setting make all items in container fit inside 

- nowrap: Every item is fit to a single line.
- wrap: Items wrap around to additional lines.
- 🌟 🌟🌟 wrap-reverse: Items wrap around to additional lineS in reverse.

```css
#pond {
  display: flex;
  flex-wrap: wrap;
  flex-direction: column
}
```

## flex-flow - Whole container 
The two properties flex-direction and flex-wrap are used so often together that the shorthand property flex-flow was created to combine them.

```css
#pond {
  display: flex;
  flex-flow: wrap column
}
```

## align-content - multiple lines 
You can use align-content to set how multiple lines are spaced apart from each other

- flex-start: Lines are packed at the top of the container.
- flex-end: Lines are packed at the bottom of the container.
- center: Lines are packed at the vertical center of the container.
- space-between: Lines display with equal spacing between them.
- space-around: Lines display with equal spacing around them.
- stretch: Lines are stretched to fit the container.

```css
#pond {
  display: flex;
  flex-wrap: wrap;
  align-content: flex-end
}
```

## 24 solution 

```css
  flex-flow: wrap-reverse column-reverse;
  justify-content: center;
  align-content: space-between;
```

## Mine 
🧠 I learn that `justify-content` and `align-items` just for items in SINGLE row (column)
`align-content` will change space between MULTIPLE row/col

## Author

This repo was developed by [@lamha](https://github.com/HaLamUs). 
Follow or connect with me on [my LinkedIn](https://www.linkedin.com/in/lamhacs). 

## License
