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
- Create a multi-column, responsive image gallery using floats

> Annotation: The students have proven that they already understand this material so I am adding a new lesson
> that covers Responsive Design using floats and bridges the gap to Responsive Design using css breakpoints.

### Preparation
*Before this lesson, students should already be able to:*

- Write basic HTML and CSS
- Use the Chrome dev tools
- Use CSS Box Model properties such as margin and padding
- Use float to create multiple columns in a web page

## Opening - Responsive Design in a nutshell (5 mins "I DO")

Today, more than half of all web browsing takes place on small, mobile devices. But many other devices, such as tablets, laptops, or HD television monitors still represent a large enough portion of the market that we cannot disregard design for them. The problem of creating a website that can respond or adapt to viewports of varying widths is more important than ever.

We don't want to rewrite the HTML and CSS for every device we need to support so we use techniques that enable our web page to respond, or display itself differently, as the viewport width changes. There are many techniques to solve the many problems of responsive design but one of the most basic and most common is the float and clearfix method which we will now learn.

> Assessment - Fist to Five

## Float review - Codealong (10 mins "WE DO")

Let's take a minute to review CSS floats from the last section.

- Create an new directory called `responsive-float` and cd into it
- Create html page called `index.html` with an externally linked css stylesheet called `style.css`
- Inside your html page create a `<div>` with the id `container`
- Inside the container `<div>` add a `<div>` with the id `floater` and a `<p>` with 3 paragraphs of ipsum.
- Inside our CSS file, make the `container` id a 500px by 500px yellow square and make the `floater` id a 150px by 150px brown square with a margin of 10px.

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
  height: 200px;
  width: 200px;
  margin: 10px;
  background-color: brown;
}
```

In the browser, we can see the `<div>` in the upper left corner and the `<p>` with its text below it. Now add the following line to the styles for #floater:

```css
  float: left;
```

Now we can see the text in the `<p>` tag flowing around the floated `<div>`.

> Assessment - Ask if anyone did not get the text to flow around the div. Address if necessary.

## How floats create responsiveness (5 min "I DO")

A floated element allows subsequent elements to "flow around" it. This means that if there is room to the non-floated side of the element, subsequent elements will appear there. If there is no more room on the non-floated side, subsequent elements will wrap onto the next line below the floated element. So depending on the total width of the page, elements will line up horizontally and then wrap when they run out of space.

Lines of text usually have a relatively small height so you can see many lines on the non-floated side of your div and when they fill up all the available space there, they will wrap to the next line underneath the floated div. However, if you place multiple divs of the same dimensions into the container and set them **all** to `float: left` then they will all reposition themselves automatically when the width of the viewport changes. And because they are all the same width and have the same margin size, they will line up into perfect columns for us!

> Assessment - Fist to Five

## Creating a multi-column, responsive image gallery (15 mins "YOU DO")

Now we will adapt our example code into a responsive image gallery. You have the following requirements:

* Remove the <p> and add nine more <div>s (total of ten) into the container all with the class floater
* Make the container's width full-screen (leave the height alone for now)
* Add a placeholder image into each `<div>`. You can use http://lorempixel.com to generate random placeholder image using their API which is very simple. To get a 200px by 200px image of a cat, use this URL as your `<img>` src: http://lorempixel.com/200/200/cats.
* Once the code is written and the page successfully renders, adjust your browser's window width from wide to narrow to see how the floated elements automatically stack and wrap as the page becomes more narrow.

The code will be as follows:

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
    <div class="floater"></div>
    <div class="floater"></div>
</div>
```

And the CSS:

```css
#container {
  width: 100%;
  height: 500px;
  background-color: yellow;
}

.floater {
  height: 200px;
  width: 200px;
  margin: 10px;
  background-color: brown;
  float: left;
}
```

Did anyone notice that our floater `<div>`s flowed beyond the height of our `container`? This is called "overflow" and there is a very simple way to deal with it. Simply add the following line to the `#container` styles:

```css
  overflow: auto
```

This tells the container to do one of two things to deal with overflow. If the container has an explicit height property set, then the container will adhere to the height and add scrollbars to deal with overflow. If no height is set on the container, then the container will expand to encompass the overflow. Try removing the height property now to see the difference.

> Assessment - Walk around viewing students pages

## Conclusion (5 mins)

We have seen how the nature of the float property can affect simple responsiveness in a web page. A floated element allows other elements to render on the non-floated side if there is enough space. As space is used up, elements are wrapped onto subsequent lines or rows. We have also created a working, albeit very simple, example of a responsive image gallery using only floats. In the next few sections, we will learn other techniques for responsive design that give you more control over layout. The float solution is somewhat controversial in that it is not the most elegant way to achieve responsiveness, but it is a very commonly seen method in the wild. Understanding how it works is crucial in your path to become a successful web developer.
