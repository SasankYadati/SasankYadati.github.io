---
title: A Fixed Point Exercise
date: 2023-06-25 02:30:00 +0530
categories: [Math, Proofs]
tags: [math, proofs, fixed-points, exercises]     # TAG names should always be lowercase
math: true
mermaid: true
---

Proving the below theorem has me all excited so I decided to write it up neatly and publish it here. I recommend trying to prove this or even just understanding the statement of the theorem well before reading the proof. You will have way more fun attempting the proof rather than reading it!

<b>Theorem:</b> Suppose that a non-empty set $$T$$ has a function $$f$$ from $$T$$ to $$T$$ without fixed points (i.e., for all $$x, f(x) \neq x $$). There is no surjection from $$S$$ to $$T^S$$, where $$S$$ is a non-empty set[^footnote].

<b>Proof:</b> For contradiction, assume a surjection from $$S$$ to $$T^S$$ exists. Let it be $$h:S\mapsto T^S$$.<br>
Now, let $$g:S\mapsto T$$ be defined as follows:<br>
<centre>$$g(x) = f(h(x)(x))$$</centre>
Recall $$h(x)$$ maps a value in $$S$$ to a function from $$S$$ to $$T$$. This value $$h(x)$$ which is a function in itself is applied on $$x$$ again and this application is denoted as $$h(x)(x)$$, giving us an element in $$T$$. Finally we map this element using $$f$$.<br>
Since, $$h$$ is surjective. there exists $$y$$ such that $$h(y) = g$$ by definition of surjectivity. Note $$y \in S$$.<br><br>
Finally, consider $$g(y)$$:
<centre>$$g(y) = f(h(y)(y)) = f(g(y)) \neq g(y)$$</centre> (since $$f$$ has no fixed points).<br><br>
This gives us the desired contradiction. Therefore no such surjection $$h$$ can exist. $$QED.$$

<br><br>
Most steps in this proof (or most proofs) just follow from the definitions (surjectivity, non-emptiness of a set). In any proof, certain steps however seem mysterious. For example, in the above proof, you might wonder how I magically came up with such a function $$g$$. <b>I seem to have constructed it out of nowhere</b>. Many functions exist that may not lead us to a contradiction. The fact is that I have tried to construct several functions before $$g$$ where I have failed to derive a contradiction. And in all the proofs such mysterious parts only seem mysterious because the author seldom talks about all the scratch work and failed attempts. My strategy was to assume there exists a surjection and hope to find an element in the co-domain of the surjection that is not in the range. This is perhaps the art part of proofs and mathematics. This is where the fun lies! If you want to enjoy proofs, don't read them. Attempt them! That's also the only way we can get good at them.

[^footnote]: [**Fixed Point Exercises**](https://www.lesswrong.com/s/5WF3wmwvxX9TEbFXf/p/FZkLa3GRLW97fpknG)