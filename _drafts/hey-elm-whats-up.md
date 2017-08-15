---
layout: post
title: Let's do an Elm
---


Notes
---

"If you are on the fence, I can safely guarantee that if you give Elm a shot and actually make a project in it, you will end up writing better JavaScript and React code. The ideas transfer pretty easily!" - [source](https://guide.elm-lang.org/)

WE'LL SEE.

---

My first Elm error (from the repl):

```
> 'taco'
-- SYNTAX PROBLEM -------------------------------------------- repl-temp-000.elm

Elm uses double quotes for strings. Switch the ' to " on both ends of the string
and you should be all set!

3|   'taco'
          ^
Maybe <http://elm-lang.org/docs/syntax> can help you figure it out.
```

They weren't kidding when they said the error messages were helpful!

Another:

```
> "what" + "up"
-- TYPE MISMATCH --------------------------------------------- repl-temp-000.elm

The left argument of (+) is causing a type mismatch.

3|   "what" + "up"
     ^^^^^^
(+) is expecting the left argument to be a:

    number

But the left argument is:

    String

Hint: To append strings in Elm, you need to use the (++) operator, not (+).
<http://package.elm-lang.org/packages/elm-lang/core/latest/Basics#++>
```

---

Function declaration is a little strange to me. Arguments aren't wrapped in parentheses. Function body isn't wrapped in brackets.

Whitespace is significant.

This is anarchy.

---

So we have tuples. OK, I've heard of these. I still don't understand the use case. It's like a fixed-length array of mixed types.

Alright, but why not use an object (or as Elm calls it, a record).

What are tuples doing that is special?

---

I'm already getting used to the structure of this code. Reminds me of what little Python I've been exposed to.

Kind of crazy that indentation alone is enough to signify a block, but I think the anxiety this provokes in me is based on how powerful this feels.

---

Maybe the craziest thing I've seen so far is the this:

```
> divide x y = x / y
<function> : Float -> Float -> Float
```

is the same as:

```
> divide = \x -> (\y -> x / y)
<function> : Float -> Float -> Float
```

It's that chain of `Float`s that is so perplexing. It's not that it reads like "Here's a bunch of arguments, and the last thing is the output."

There's this idea here that each argument is sort of adding this layer of scope. Anonymous functions within anonymous functions.

Translates to:

```javascript
const divide = function(x) {
  return function(y) {
    return x / y;
  };
}

divide(3)(2);
// returns 1.5
```

This is functional programming!!!

---

Union types

Immediately reminds me of `action.type` from Redux. Perhaps because of its use in `case` expression.

I like this a lot because the way I'd deal with it in Redux is a constant like:

```Javascript
// in the action creator:
const SET_TIMER = 'SET_TIMER';

function setTimer() {
  return {
    type: SET_TIMER,
    ...
  };
}

// and then in the reducer...

import { SET_TIMER } from '../actions/timer';

switch (action.type) {
  case SET_TIMER: {
    ...
  }
}
```

This is something I don't like doing!
