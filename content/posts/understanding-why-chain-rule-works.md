---
author: "Godspower Eze"
title: "Understanding Why Chain Rule Works"
date: "2025-01-31"
description: "Showing the intuition behind differentiation by understanding rate of change and using limits"
keywords: ["differentiation", "intuition behind chain rule", "understanding differentiation", "understanding chain rule"]
tags: [
    "calculus",
    "differentiation",
]
categories: [
    "Mathematics",
]
---
## Understanding Why Chain Rule Works

> _"Mathematical intuition is the ability to see the truth without first having gone through a formal process of reasoning."_  
> — Henri Poincaré

The goal of this post is to force you to think about the chain rule a bit deeply.

The only prerequisite for reading this is understanding the power rule(i.e $\dfrac{d}{dx}[x^n] = nx^{n-1}$). Understanding <a href="{{< ref "intuition-behind-differentiation.md" >}}" target="_blank">differentiation intuitively</a> is recommended.

The chain rule is a differentiation method for composite functions. It is defined as follows for a function $f(u)$ where $u = g(x)$  $$\dfrac{d}{dx}[f(u)] = \dfrac{d}{du}f(u)*\dfrac{d}{dx}(u)$$
which implies differentiate $f(u)$ with respect to $u$ treating $u$ as an independent variable, and differentiate $g(x)$ with respect to $x$ and then multiply both.

For example, given the function $f(x) = (2x^2 + 10)^2$, we can differentiate it as follows: we would set $g(x) =  2x^2 + 10$ and $u = g(x)$ so we can express $f(g(x))$ as $f(u) = u^2$.

Now, let's use the chain rule: $\dfrac{d}{du}f(u) = 2u$, $\dfrac{d}{dx}(u) = 4x$ and  $\dfrac{d}{dx}[f(u)] = 2u*4x$. Recall that $u = g(x) = 2x^2 + 10$, so we have $\dfrac{d}{dx}[f(u)] = 2(2x^2 + 10)*4x = 16x^3 + 80x$.

---

To understand the chain rule, you must first understand how function compositions work.

If we have a functions $f(x)$ and $g(x)$, what does $f(g(x))$ mean?

It means that for the function $f(x)$, evaluate it at $g(x)$ instead of $x$. We want to study the effect of this change.

How does $f(g(x))$ change with respect to a change $x$? Another way to put it is this: how does $f(g(x))$ change with respect to $g(x)$ and $g(x)$ with respect to $x$?

Let's explore the behaviour of change in a function composition.

**Example 1**: For $g(x) = 2x$ and $f(x) = x^2$ for an interval $x \in [-4,  4]$.

Let's see the graph:

<iframe src="https://www.desmos.com/calculator/yimwy1fmsz?embed" width="700" height="700" style="border: 1px solid #ccc" frameborder=0></iframe>

Let's build the intuition for this by looking at the table of values of $g(x)$, $f(x)$ $f(g(x))$ and $\dfrac{d}{dx}[f(g(x))]$ on the interval.

| $x$  | $g(x) = 2x$ | $\dfrac{d}{dx}[g(x)] = 2$ | $f(x) = x^2$ | $\dfrac{d}{dx}[f(x)] = 2x$ | $f(g(x)) = 4x^2$ | $\dfrac{d}{dx}[f(g(x))] = 8x$ |
| ---- | ----------- | ------------------------- | ------------ | -------------------------- | ---------------- | ----------------------------- |
| $-4$ | $-8$        | $2$                       | $16$         | $-8$                       | $64$             | $-32$                         |
| $-3$ | $-6$        | $2$                       | $9$          | $-6$                       | $36$             | $-24$                         |
| $-2$ | $-4$        | $2$                       | $4$          | $-4$                       | $16$             | $-16$                         |
| $-1$ | $-2$        | $2$                       | $1$          | $-2$                       | $4$              | $-8$                          |
| $0$  | $0$         | $2$                       | $0$          | $0$                        | $0$              | $0$                           |
| $1$  | $2$         | $2$                       | $1$          | $2$                        | $4$              | $8$                           |
| $2$  | $4$         | $2$                       | $4$          | $4$                        | $16$             | $16$                          |
| $3$  | $6$         | $2$                       | $9$          | $6$                        | $36$             | $24$                          |
| $4$  | $8$         | $2$                       | $16$         | $8$                        | $64$             | $32$                          |

The graph shows that the maximum value for $f(x)$ is $16$ while that of $f(g(x))$ is $64$. That's a scale-up.

Can you see a pattern? Every value of $f(g(x))$ is $4$ times the value of $f(x)$.

We can show this formally by picking any two unique pairs of $f(x)$ and $f(g(x))$ (i.e at the same $x$) and finding the slope(i.e $\dfrac{y_2 - y_1}{x_2 - x_1}$). For example, using the pairs ($16$, $64$) and ($4$, $16$), we have $\dfrac{64 - 16}{16 - 4} = \dfrac{48}{12} = 4$. Let's use another two pairs ($9$, $36$) and ($1$, $4$), we have $\dfrac{4 - 36}{1 - 9} = \dfrac{-32}{-8} = 4$

This turns out to be easy to see because $f(g(x))$ is simply $4$ times $f(x)$ so it makes sense that this is the case. Other places you can notice is as follows:

- The values of $\dfrac{d}{dx}[f(g(x))]$ is 4 times the values of $\dfrac{d}{dx}[f(x)]$
- Every value of $f(g(x))$ and $\dfrac{d}{dx}[f(g(x))]$ is divisible by $4$
- The  difference between any two values of $f(g(x))$ and $\dfrac{d}{dx}[f(g(x))]$ is divisible by $4$
The means that for every change in the value of $f(x)$ there's a 4x change in the value of $f(g(x))$. This sounds weird, right? we just represented the rate of change between two somewhat independent functions as if they were dependent on each other. If this relationship was a function it would be $h(x) = 4x$ so that $\dfrac{d}{dx}[h(x))] = 4$. This works because $f(g(x))$ is a composition of $f(x)$ and $g(x)$ and $f(x) = x^2$.

Let's try this for $x$ and $g(x)$. But then, you might ask: Is $g(x)$ a composition of $x$? Let's see.

If we created a function $v(x) = x$, then $g(v(x))$ equals $g(x)$. This is true for every function of $x$. Having set this foundation, we can see that for every change in $x$, $g(x)$ by a factor of $2$.

**Note**: You won't always have a constant factor between $f(x)$ and $f(g(x))$ or between their derivatives. But most times $g(x)$ would affect the behaviour of change in the $f(g(x))$ compared to $f(x)$. It either makes it **faster**, **slower**, **scale-up**, **scale-down** and even combination of these along certain intervals.

The examples below show some of these other behaviours of change.

**Example 2**: For $g(x) = -x$ and $f(x) = x^3$ for an interval $x \in [-3,  3]$.

<iframe src="https://www.desmos.com/calculator/ozvt0afldc?embed" width="700" height="700" style="border: 1px solid #ccc" frameborder=0></iframe>

| $x$  | $g(x) = -x$ | $\dfrac{d}{dx}[g(x)] = -1$ | $f(x) = x^3$ | $\dfrac{d}{dx}[f(x)] = 3x^2$ | $f(g(x)) = -x^3$ | $\dfrac{d}{dx}[f(g(x))] = -3x^2$ |
| ---- | ----------- | -------------------------- | ------------ | ---------------------------- | ---------------- | -------------------------------- |
| $-3$ | $3$         | $-1$                       | $-27$        | $27$                         | $27$             | $-27$                            |
| $-2$ | $2$         | $-1$                       | $-8$         | $12$                         | $8$              | $-12$                            |
| $-1$ | $1$         | $-1$                       | $-1$         | $3$                          | $1$              | $-3$                             |
| $0$  | $0$         | $-1$                       | $0$          | $0$                          | $0$              | $0$                              |
| $1$  | $-1$        | $-1$                       | $1$          | $3$                          | $-1$             | $-3$                             |
| $2$  | $-2$        | $-1$                       | $8$          | $12$                         | $-8$             | $-12$                            |
| $3$  | $-3$        | $-1$                       | $27$         | $27$                         | $-27$            | $-27$                            |

**Example 3**: For $g(x) = x + 1$ and $f(x) = x^2+x$ for an interval $x \in [-2,  2]$.

<iframe src="https://www.desmos.com/calculator/1snsjfddwm?embed" width="700" height="700" style="border: 1px solid #ccc" frameborder=0></iframe>

| $x$  | $g(x) = x + 1$ | $\dfrac{d}{dx}[g(x)] = 1$ | $f(x) = x^2 + x$ | $\dfrac{d}{dx}[f(x)] = 2x + 1$ | $f(g(x)) = x^2 + 3x + 2$ | $\dfrac{d}{dx}[f(g(x))] = 2x + 3$ |
| ---- | -------------- | ------------------------- | ---------------- | ------------------------------ | ------------------------ | --------------------------------- |
| $-2$ | $-1$           | $1$                       | $2$              | $-3$                           | $0$                      | $-1$                              |
| $-1$ | $0$            | $1$                       | $0$              | $-1$                           | $0$                      | $1$                               |
| $0$  | $1$            | $1$                       | $0$              | $1$                            | $2$                      | $3$                               |
| $1$  | $2$            | $1$                       | $2$              | $3$                            | $6$                      | $5$                               |
| $2$  | $3$            | $1$                       | $3$              | $5$                            | $12$                     | $7$                               |

---
Chain rule answers the question: _how do you express a function dependent on a variable as the rate of change in respect to that variable when the variable is a function?_

### Why is $g(x)$ treated like a variable?

In the chain rule why are we differentiating in respect to $g(x)$ as if it was a variable? This is simply because it is.

The intuition is the definition of the behaviour of change in a composite function: as $g(x)$ changes $f(g(x))$ and as $x$ changes $g(x)$.

$g(x)$ is a variable in $f(g(x))$ so it's treated as such when represent the change in $f(g(x))$

### Why is the change in $g(x)$ multiplied by the change in $f(g(x))$?

This is simply because as $x$ changes $g(x)$ changes and that's a _factor_ affecting the change in $f(g(x))$.

### Why Multiplication(and Not Addition)?

Why is the chain rule $\dfrac{d}{dx}[f(u)] = \dfrac{d}{du}f(u)*\dfrac{d}{dx}(u)$ and not $\dfrac{d}{dx}[f(u)] = \dfrac{d}{du}f(u)+\dfrac{d}{dx}(u)$?

The intuition is in the definition: as $g(x)$ changes $f(g(x))$ _and_ as $x$ changes $g(x)$. For clarity: Let's break this statement into three part:

- as $g(x)$ changes $f(x)$ - $g(x)$ is treated as a variable
- $x$ changes $g(x)$
- _and_ - from binary operations, we know that _and_  implies multiplication. just like _or_ implies addition.

---
I hope you were able to think wide and far about function compositions and the chain rule!
