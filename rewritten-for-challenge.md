---
title: Responsive Design with CSS Floats
type: lesson
duration: "0:35"
creator:
    name: Steve Peters
    city: Seattle
competencies: Front-end intro
---

# Responsive Design with CSS Floats

### Objectives
*After this lesson, students will be able to:*

- Explain how float is used to create responsive web pages
- Create a multi-column, responsive site using floats

> Annotation: The students have proven that they already understand this material so I am adding a new lesson
> that covers Responsive Design using floats.

### Preparation
*Before this lesson, students should already be able to:*

- Use CSS Box Model properties
- Use float to create multiple columns in a web page

## Opening - Responsive Design in a nutshell (5 mins "I DO")

Today, more than half of all web browsing takes place on small, mobile devices. But many other devices, such as tablets, laptops, or HD television monitors still represent a large enough portion of the market that we cannot disregard design for them. The problem of creating a website that can respond or adapt to viewports of varying widths is more important than ever.

We don't want to rewrite the HTML and CSS for every device we need to support so we use techniques that enable our web page to respond as the viewport width changes.

> Assessment - Fist to Five

## Float review - Codealong (10 mins "WE DO")

Let's take a minute to review CSS floats from the last section.

- Create an new directory called `responsive-float`
- Create html page called `index.html` with an externally linked css stylesheet called `style.css`
- Inside your html page create a `<div>` with the id `container`
- Inside the container `<div>` add a `<div>` with the id `floater` and a `<p>` with 3 paragraphs of ipsum.
- Inside our CSS page, make the `container` id a 500px by 500px yellow square and make the `floater` id 150px by 150px with a `background-color` of brown.

Looking at the html:

```html
<link rel="stylesheet" type="text/css" href="css/style.css">

<div id="container">
  <div id="floater"></div>
  <p>3 paragraphs of lorem ipsum...</p>
</div>
```

And the css:

```css
#container {
  width: 500px;
  height: 500px;
  background-color: yellow;
}

#floater {
  height: 150px;
  width: 150px;
  background-color: brown;
}
```

In the browser, we can see the `<div>` in the upper left corner and the `<p>` with its text below it. Now add the following line to the styles for #floater:

```css
  float: left;
```

Now we can see the text in the `<p>` tag flowing around the floated `<div>`.

> Annotation: Assessment - 

## Creating a multi-column responsive page (15 mins "YOU DO")

Now remove the <p> and add seven more divs into the container all with the class floater.

```html
<link rel="stylesheet" type="text/css" href="css/style.css">

<div id="container">
    <div class="floater"></div>
    <div class="floater"></div>
    <div class="floater"></div>
    <div class="floater"></div>
    <div class="floater"></div>
    <div class="floater"></div>
    <div class="floater"></div>
    <div class="floater"></div>
</div>
```

And the CSS:

```css
#container {
    background-color: gray;
    position: relative;
    width: 100%;
    overflow: auto;
}

.floater {
  height: 400px;
  width: 300px;
  background-color: red;
  float: left;
  margin: 16px;
}```




400px divs

> Annotation: Assessment - 

## Conclusion (5 mins)
