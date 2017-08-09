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
> 1/2
0.5 : Float
> 4
4 : number
> 4.0
4 : Float
> 'taco'
-- SYNTAX PROBLEM -------------------------------------------- repl-temp-000.elm

Elm uses double quotes for strings. Switch the ' to " on both ends of the string
and you should be all set!

3|   'taco'
          ^
Maybe <http://elm-lang.org/docs/syntax> can help you figure it out.


> "taco"
"taco" : String
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
