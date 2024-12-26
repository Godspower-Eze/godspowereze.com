---
author: "Godspower Eze"
title: "Intuition Behind Differentiation"
date: "2024-11-19"
description: "Sample article showcasing basic Markdown syntax and formatting for HTML elements."
keywords: ["differentiation"]
tags: [
    "calculus",
    "differentiation"
]
categories: [
    "Math Intuition",
]
series: ["Themes Guide"]
aliases: ["migrate-from-jekyl"]
---
For $y = f(x)$, differentiation is the ratio of **how $y$  changes** as **$x$ changes**. This is the rate of change of the function.

For a straight line, this would be constant. For example, the derivative of $f(x)=2x + 1$ is 2. This is the good old slope of a graph(the ratio of change in $y$ to the change in $x$: $\dfrac{y_2 - y_1}{x_2 - x_1}$)

But then, how do we find the rate of a change of a function that's a curve?

We could decide to find the slope using $\dfrac{y_2 - y_1}{x_2 - x_1}$ but this only tells us the rate of change between certain intervals in $x$. It doesn't represent change in the whole function. This might be useful in some cases but how do we get the rate of change in the function as a whole.

We know that the slope can't be constant because it's a curve so we resort to finding the instantaneous rate of change. We may not be able to find the rate of change of the whole curve but can find the rate of change of the curve in an *instant*.

An *instant* can be a seen as a moment. How do you represent a moment in time?

If we had a function of time $t$, $f(t)$, this can be seen a value of $t$ close to zero but not zero. It is popularly called an *infinitesimal* value of $t$. How do we represent *$t$ close to zero but not zero*? We use [limits](https://byjus.com/maths/limits/)! This can be represented as follow:$$\lim_{\Delta t \to 0}\dfrac{f(t+\Delta t) - f(t)}{(t +\Delta t) - t} = \lim_{\Delta t \to 0}\dfrac{f(t+\Delta t) - f(t)}{\Delta t}$$This looks a lot like the formula for finding slope but our interval here is $t$ to $t$ plus an infinitesimal value of $t$. This reads "the change in the function $f(x)$ as the change in time $t$ approaches zero". $\Delta t$ is the change in time.

Let using the limit formula to derive the slope of the function $f(x) = 2x + 1$.$$f(x + \Delta x) = 2(x + \Delta x) + 1 = 2x + 2\Delta x + 1$$$$\lim_{\Delta t \to 0}\dfrac{f(x +\Delta x) - f(x)}{\Delta x}=\lim_{\Delta t \to 0}\dfrac{2x + 2\Delta x + 1-(2x + 1)}{\Delta x} $$$$=\lim_{\Delta t \to 0}\dfrac{2x + 2\Delta x + 1- 2x - 1}{\Delta x}=\lim_{\Delta t \to 0}\dfrac{2\Delta x}{\Delta x}$$$$=2$$We have been able to come up with a generalized rate of change for our striaght line function above. You can confirm this by picking two arbitrary values of $x_1$ and $x_2$ and computing $\dfrac{y_2 - y_1}{x_2 - x_1}$.

But, then this really shines for function other than straight line functions. Let's try this on a quadratic $g(x) = x^2 + 5x - 3$. For better visuals we would set $h = \Delta x$ $$g(x + h) = (x + h)^2 + 5(x + h) - 3$$$$=x^2 + 2xh + h^2 + 5x + 5h - 3$$
$$\lim_{h \to 0}\dfrac{f(x + h) - f(x)}{h}$$ $$\lim_{h \to 0}\dfrac{x^2 + 2xh + h^2 + 5x + 5h - 3 - (x^2 + 5x - 3)}{h}$$$$=\lim_{h \to 0}\dfrac{x^2 + 2xh + h^2 + 5x + 5h - 3 - x^2 - 5x + 3}{h}$$$$=\lim_{h \to 0}\dfrac{2xh + h^2 + 5h}{h}$$$$=\lim_{h \to 0}\dfrac{2xh}{h}+\dfrac{h^2}{h}+\dfrac{5h}{h}$$$$=\lim_{h \to 0}2x+ h + 5$$$$=2x + 0 + 5$$$$=2x + 5$$This simply means that at any point $x$ we can compute the rate of change in that *moment* using $2x + 5$.

This is the fundamental idea behind differentiation.
