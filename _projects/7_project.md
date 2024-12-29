---
layout: page
title: Implicit Regularization of Gradient Descent
description: March 2024 - May 2024
img: assets/img/cover_image_1.png
importance: 1
category: statistics/mathematics
related_publications: false
---
<hr style="border: 1px solid black; width: 100%;">

This is a project I did with **Mriganka Basu Roy Chowdhury**, who was in his fourth year PhD with Prof. Shirshendu Ganguly in the stats department. It's a final project for a special topics graduate class in **statistical learning**, and we ended up completing a report of **13 pages**. In April, I presented the relevant theory in a **BLISS seminar** to our group. We received a **69/70** for the project.

<hr style="border: 1px solid black; width: 100%;">

Our starting point was **Reproducing Kernel Hilbert Space** theory. Mriganka found a <a href='https://cgad.ski/blog/when-gradient-descent-is-a-kernel-method.html'> blog post</a> where the author considered a linear regression problem on a large set of random functions. The constraint is that my function must go through very few number of points, few comparing to the size of my function set, which means many solutions would satisfy this condition. Now, I can run gradient descent on this set to obtain one solution, but the observation comes quite visually--as the website has a visual simulation--that GD would produce a solution that puts straight lines between my constraint points. One can view straight line between points as a minimization of some sort of distance or norm. The idea is: GD shouldn't be treated as just another optimization method, and it performs an implicit regularization on the solution. 

We then dived into this topic with the standard approach, which is to consider the **least squares** problem. From there, one can show, by solving the gradient flow differential equations, that running GD would produce a solution that minimizes the l-2 norm. This seems to be consistent with the blog post from above. 

From here, we shifted our attention to one question: is it true that in any problem setting, implicit regularization always means implicit norm regularization. The answer is no. Following <a href='https://arxiv.org/abs/2005.06398'> this paper</a>, we were able to show both theoretically and empirically that GD regularizes towards rank but not norm in the context of the **matrix factorization** problem. In this case, it is important because matrix factorization bears similarity to neural networks, and since GD or its variations is almost the only method used in neural networks, knowing the natrue of GD's implicit regularization becomes increasingly important. 

<html>

<head>
    <title>PDF in HTML</title>
</head>
<style>
    .pdf {
        width: 100%;
        aspect-ratio: 4 / 3;
    }
    .pdf,
    html,
    body {
        height: 100%;
        margin: 0;
        padding: 0;
    }
   h1,
    h3 {
        text-align: center;
    }

    h1 {
        color: green;
    }
</style>

<body>
        <iframe class="pdf" 
                src=
"https://wjingxing.github.io/assets/pdf/imp.pdf"
            width="800" height="500">
        </iframe>
</body>

</html>

**End**
