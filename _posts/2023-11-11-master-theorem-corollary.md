---
layout: post
title: Corollary of the Master Theorem
date: 2023-11-11 16:10:51-0400
description: a proof that T(n) = T(n/2) + Θ(log^k n) solves to Θ(log^(k+1) n)
tags: algorithms math
categories: notes
related_posts: false
---

## Introduction

After a really long time, I decided to update this website. We will see if I can keep this consistent. This time, I will provide my sample proof of one corollary of the Master Theorem, which I will call the Master-Like Theorem. The problem is:

If $$T(n) = T(n/2) + \Theta(\log^k n)$$ and $$T(1) = \Theta(1)$$, for some fixed integer $$k \geq 0$$, then

$$
T(n) = \Theta(\log^{k+1} n)
$$

For this problem, we can first draw the recurrence table.

| Level | Problem Size      | Cost Per Problem   | Total Cost         |
| ----- | ----------------- | ------------------ | ------------------ |
| 0     | $$n$$             | $$c\log^k n$$      | $$c\log^k n$$      |
| 1     | $$n/2$$           | $$c\log^k (n/2)$$  | $$c\log^k (n/2)$$  |
| d     | $$n/2^d$$         | $$c\log^k (n/2^d)$$ | $$c\log^k (n/2^d)$$ |
| L     | $$n/2^L = 1$$     | $$c^\prime$$       | $$c^\prime$$       |

From this table, we can tell that the last level satisfies $$n/2^L = 1$$, so there are $$\log_2 n$$ levels in total. Based on this number, we can work out the total cost.

$$
c\cdot\sum^{(\log_2n) -1}_{d=0}\log^k(n/2^d) + c^\prime
$$

We can make a transformation to make it look nicer.

$$
c \cdot \sum^{\log_2 n -1}_{d=0}(\log_2 n - \log_2 2^d)^k + c^\prime
$$

After we have the correct expression for the total cost, we need to prove it lies in the range bounded by Big-Oh and Big-Omega. We have to prove them separately. I will start with the Big-Oh case because it's more intuitive and also turns out to be much easier.

#### Case Big-Oh

Since $$\log_2 2^d = d$$ and $$d \geq 0$$, $$(\log_2 n - \log_2 2^d)^k$$ will always be smaller than $$\log^k_2 n$$. This shows that

$$
\begin{aligned}
    c \cdot \sum^{\log_2 n -1}_{d=0}(\log_2 n - \log_2 2^d)^k + c^\prime &\leq c \cdot \sum^{\log_2 n -1}_{d=0}(\log_2 n)^k + c^\prime \\
    c \cdot \sum^{\log_2 n -1}_{d=0}\log^k_2 (n/2^d) + c^\prime &\leq c \cdot \sum^{\log_2 n -1}_{d=0}(\log_2 n)^k + c^\prime  \\
    &= c \cdot \log_2 n \cdot (\log_2 n)^k + c^\prime \\
    &= c \cdot \log^{k+1}_2 n + c^\prime
\end{aligned}
$$

Because $$c$$ and $$c^\prime$$ are both constants, let $$g(n) =\log^{k+1}_2 n$$ and $$f(n) =\sum^{\log_2 n -1}_{d=0}\log^k (n/2^d) + c^\prime$$. If there are $$c, N> 0$$ such that

$$
f(n) \leq c \cdot g(n)
$$

for all $$n \geq N$$, then

$$
f(n) = O(g(n)) = O(\log^{k+1}_2 n)
$$

This finishes the proof for the Big-Oh case. One thing to notice is that I use log base 2 in my proof, but I think this can be generalized to any base because you can do the change-of-base trick. It may be worth exploring whether the proof becomes easier with a specified base.

#### Case Big-Omega

This will be a lot harder. Expanding the total work we got from the table, the summation part will be

$$
(\log_2 n )^k + (\log_2 n -1)^k + (\log_2 n -2)^k + \dots + 2^k + 1^k
$$

We can then transform these sums into

$$
\sum^{\log_2 n}_{d=1} d^k
$$

which satisfies

$$
\sum^{\log_2 n}_{d=\frac{\log_2 n}{2}} d^k \leq \sum^{\log_2 n}_{d=1} d^k
$$

Since on the left side of the inequality $$d$$ goes from $$\frac{\log_2 n}{2}$$ to $$\log_2 n$$, we can replace $$d$$ in $$d^k$$ with $$\frac{\log_2 n}{2}$$ to get a new inequality:

$$
\sum^{\log_2 n}_{d=\frac{\log_2 n}{2}} \left(\frac{\log_2 n}{2}\right)^k \leq \sum^{\log_2 n}_{d=\frac{\log_2 n}{2}} d^k
$$

The left side's sum will be

$$
\left(\frac{\log_2 n}{2} + 1\right) \cdot \left(\frac{\log_2 n}{2}\right)^k = \frac{\log^{k+1}_2 n}{2^{k+1}} + \frac{\log^k_2 n}{2^k} \geq \frac{\log^{k+1}_2 n}{2^{k+1}}
$$

Overall, we can put all the inequalities together:

$$
\frac{\log^{k+1}_2 n}{2^{k+1}} \leq \sum^{\log_2 n}_{d=\frac{\log_2 n}{2}} \left(\frac{\log_2 n}{2}\right)^k \leq
\sum^{\log_2 n}_{d=\frac{\log_2 n}{2}} d^k \leq \sum^{\log_2 n}_{d=1} d^k = \sum^{\log_2 n -1}_{d=0}\log^k (n/2^d)
$$

Since $$k$$ is a constant and $$k \geq 0$$, $$\frac{1}{2^{k+1}}$$ is also a constant bigger than 0. Let $$c = 1/2^{k+1}$$, $$N > 0$$, $$g(n) = \log^{k+1}_2 n$$, and $$f(n) = \sum^{\log_2 n -1}_{d=0}\log^k (n/2^d)$$. Then

$$
f(n) \geq c \cdot g(n)
$$

for all $$n \geq N$$, so

$$
f(n)  = \Omega(g(n)) = \Omega(\log^{k+1}_2 n)
$$

Overall, since $$f(n)$$ is both $$O(\log^{k+1}_2 n)$$ and $$\Omega(\log^{k+1}_2 n)$$,

$$
f(n) = \sum^{\log_2 n -1}_{d=0}\log^k (n/2^d) = \Theta(\log^{k+1}_2 n)
$$

which also means

$$
T(n) =\Theta(\log^{k+1}_2 n) \qquad \blacksquare
$$

The main idea is to shrink a large summation into a simpler expression that is still smaller than it, and show that this expression is already in the Big-Omega range.
