---
layout: default
---

# Week 02

[← Back to Home](../index.md)

# DES240 Experiment 2: Interactivity

## Pair Exchange of Data Portrait

![Pair exchange photo](../assets/week-02/pair-exchange-food-portrait.jpg)
*Pair exchange discussion about my Week 01 food data portrait.*

In the pair exchange, I showed my Week 01 data portrait based on five days of tracking breakfast, lunch, and dinner. I recorded what I ate, the time, my mood, and my energy level for each meal. Explaining the drawing out loud helped me see which parts of the portrait were doing the most work. The repeated lunches were very obvious, while breakfast and dinner showed more variation. My partner also understood the mood and energy parts quite quickly, which made me feel that the hand-drawn version was already communicating more than just a meal log.

The discussion also helped me decide what to carry forward into code. I did not need to translate every part of the drawing. The most interesting parts were time, repetition, mood, and energy, because those are the things that become clearer when a viewer can filter, compare, and hover over details. That conversation gave me the direction for my interactive sketch later in the week.

## Experiment of p5.js

![Simple p5.js composition](../assets/week-02/simple-composition.png)
*My first p5.js composition using basic shapes.*


[Try it on p5.js Editor](https://editor.p5js.org/Jeffcai0502/full/eMtGVQ7Cr)

To get comfortable with the p5.js editor, I started with a very simple composition. I made a small breakfast-table scene using `rect()`, `ellipse()`, `triangle()`, and `line()`. The point of this was not to make a complicated image, but to understand how the canvas works, how shapes are layered, and how changing the order of instructions affects the final result. I also experimented with colour, stroke weight, and position.

What I noticed straight away was that coding a picture feels very different from drawing by hand. In a sketchbook I usually think visually first, but in p5.js I had to think in steps. The image only worked once I understood the order that things were drawn. That made the canvas feel less like a blank page and more like a system.

```js
function draw() {
  background(245, 248, 252);
  rect(0, 260, width, 90);
  ellipse(250, 235, 180, 70);
  triangle(80, 130, 130, 40, 180, 130);
}
```

## Make an Interactive Sketch

[Try it on p5.js Editor](https://editor.p5js.org/Jeffcai0502/sketches/jFes-66an)

![Interactive DOM sketch](../assets/week-02/interactive-food-controls.png)
*Interactive sketch using sliders, a button, and a text input.*

After that, I made a small interactive sketch using DOM controls. I kept the visual simple so I could focus on how the controls changed the canvas. In this sketch, a slider changes the size of the food on the plate, another slider moves it horizontally, a button randomises the colour, and a text input lets me rename the dish. This was my first time seeing how page elements and canvas drawing could work together.

The most useful part of this exercise was the immediacy. With a hand-drawn image, the viewer mostly receives a finished result. With DOM elements, the viewer actively changes the drawing. Even with a very basic setup, that changed the feeling of the work. It started to make sense why the course frames buttons, sliders, and inputs as digital equivalents of physical interaction.

```js
sizeSlider = createSlider(40, 180, 100);
positionSlider = createSlider(160, 340, 250);
labelInput = createInput('toast');
colourButton = createButton('change food colour');
```

## Build a More Ambitious Interactive Sketch

[Try it on p5.js Editor](https://editor.p5js.org/Jeffcai0502/sketches/4k7gkyXDJ)

![More ambitious interactive sketch](../assets/week-02/meal-picker.png)
*More ambitious p5.js sketch with multiple controls and a simple animation.*

For the next step, I wanted to make something that felt a bit more playful. I built a meal picker that lets the viewer choose breakfast, lunch, or dinner, then spin through a short set of meals collected from my Week 01 tracking. The sketch includes a dropdown menu, a spin button, and a checkbox for showing recent results. It is still simple, but it feels more like a small interactive experience rather than just a controlled drawing.

What I liked about this stage was that the code stopped feeling purely technical. Variables, arrays, and conditional logic were not just there to make the program run; they shaped the experience of the viewer. The sketch also made me think about interactivity as pacing. The short animation before the final meal appears makes the result feel more engaging, even though the underlying data is still small and personal.

## Independent Study: Interactive Data Portrait

[Try it on p5.js Editor](https://editor.p5js.org/Jeffcai0502/sketches/T0TGwrdxj)

![Interactive data portrait overview](../assets/week-02/interactive-data-portrait-overview.png)
*Overview of my interactive data portrait based on five days of meals.*

![Interactive data portrait detail](../assets/week-02/interactive-data-portrait-detail.png)
*Hover state showing detailed meal information.*

For the independent study task, I translated my Week 01 hand-drawn portrait into a p5.js data portrait. I used the same five-day dataset: breakfast, lunch, and dinner across five days, with the time, what I ate, mood level, and energy level for each meal. Instead of trying to reproduce the drawing exactly, I focused on what interaction could add.

I chose to represent each meal as a circle on a timeline. The x-position shows the time of day, each row represents a different day, the colour shows whether the meal is breakfast, lunch, or dinner, and the circle size responds to energy. I added small mood dots above each meal so mood and energy stay separate rather than getting collapsed into one value. This decision came directly from my hand-drawn portrait, where I wanted mood and energy to remain related but distinct.

The interactive controls are what make this version more useful than the original drawing. A dropdown lets the viewer switch between all five days or focus on a single day. A slider changes the circle scale so it becomes easier to compare energy visually. A checkbox toggles text labels on and off, which helps balance readability and visual clutter. I also added hover states so the viewer can inspect one meal closely without crowding the whole screen with text all the time.

Testing it with another person was useful because I could watch what they reached for first. They immediately tried the day filter before anything else, which told me comparison across days was one of the strongest parts of the sketch. They also hovered over the circles to check exact times and foods, which confirmed that hiding detail until interaction was the right choice. If all that information had stayed visible at once, the sketch would have become too dense.

What a viewer can learn here that they could not learn as easily from the hand-drawn portrait is the relationship between repetition and feeling. The repeated lunches become very obvious when all the days line up in rows, and the hover states make it easier to notice that repeated foods do not always match the same mood or energy. That was one of the most interesting things for me too. Even when the meals repeated, my state did not repeat exactly.

Working this way also changed how I think about data drawings more broadly. The hand-drawn portrait from Week 01 felt personal because of its marks, spacing, and imperfections. The p5.js version feels personal in a different way: it lets the viewer move through the data at their own pace. I think the two formats support each other well. The drawing captures the texture of lived experience, while the interactive version makes patterns easier to compare.

If I developed this further, I would add a smoother transition when switching days, and I would experiment with letting the viewer compare mood and energy separately using a second visual mode. I would also like to try adding a weekly summary panel that automatically counts repeated meals and average mood. Overall, this week helped me understand that interaction is not just an extra feature. It can be part of how data becomes readable, exploratory, and meaningful.

## Notes from Tutorials

![Tutorial notes](../assets/week-02/tutorial-notes.png)
*Short notes from testing variables, `draw()`, and data mapping.*

Outside of the main exercises, I also looked back over the basic p5.js ideas that made the bigger sketch possible. The most important ones for me were variables, the `draw()` loop, and mapping values from one range into another. Once I understood that a canvas is constantly being redrawn, it became much easier to understand animation, hover states, and interactive feedback.

Two lines that were especially useful for my data portrait were:

```js
let x = map(entry.minutes, 420, 1260, 120, width - 70);
let diameter = entry.energy * sizeSlider.value();
```

These lines helped me translate a lived routine into a visual system. Time becomes position, and energy becomes scale. That shift from everyday observation into a responsive visual structure is what made this week feel connected to the course as a whole.
