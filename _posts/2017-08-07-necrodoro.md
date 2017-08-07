# Bloggin'

So here I am, writing a blog post. Here we go. ALRIGHT.

## What It's All About

I made this thing. It's a timer for the pomodoro technique, but with some occult stuff thrown in on top. I originally intended for the narrative element to be more interactive, but it didn't really work out. I'll get into that a little bit later.

## Some Good Things

It uses React, Redux, styled-components, webpack, babel. To date, this is probably the best React app I've written, even if I'm sure to look back at it in a few months and hate the code. But I can at least say I had an idea, and I built the damn thing.

I also had a great time doing the pixel art. I have to remember to keep practicing making visuals, because I really like doing it.

## Some Bad Things

Redux, man. What the fuck. Right off the bat, I thought it would be a good idea to separate chunks of the app by their reducers. So the timer would have its reducer, the message box would have a reducer, et cetera.

But it got a little hairy when I wanted to use a piece of the timer's state in the messages reducer (the litCandles variable, which wound up being a good way to measure progress through the pomodoro cycle). But if I wanted that, I had to do a really annoying, round-about thing that involved bringing that variable into the props of a component and then sending the prop as an argument in an action creator. Just so I could do some bit of logic that ultimately went to a different reducer.

Kind of made me think, why am I even splitting this up into different reducers? Wouldn't it have been easier if I started with one big fat reducer and then considered breaking it up later?

## Lessons For the Future

I've really got to get it in my head that software needs to be designed before it's developed. I've got this bad habit of just jumping into code right away and trying to hack my way out. And it doesn't work! Ultimately, I was unable to achieve my original goal of something akin to interactive fiction, with a tree-like narrative structure.

Why? Because I thought I could just build a component, wire it into Redux, and then build the next component. I didn't really have a sense for how the whole thing would work together. I just assumed I'd figure it out later.

Well, especially with Redux, where a single part of the application has one or more components, action creators, and a reducer, it kind of became a headache to try to remember what all was happening already.

I guess the point is, I want to start writing code from the top-down, rather than from the bottom-up.
