---
title: Enumerability
date: 2023-06-25 02:30:00 +0530
categories: [Math, Computation]
tags: [math, computation, sets]     # TAG names should always be lowercase
math: true
mermaid: true
---

> We define enumerability in mathematics to capture the intuitive notion of countability. When we define a set containing infinite number of elements, certain properties hold only if the elements of the structure are countable. Yes, there are sets that are not countable. But what is this notion of countable? 
{: .prompt-tip }

# What do we mean by countable?

So, what is countable? A finite collection of items definitely seems to be a countable collection. What about infinite set? Can we count the set of natural numbers? I think so. Let me try: $1,2,3,4…$

Wait a minute! That’s only 4. What about 5? I am sure there are even more after. There are in fact infinite number of them! YOU CANNOT COUNT THEM ALL.

However, we seem to have this nice property: give me any natural number $n$ it will come up eventually if I continue counting as above (it will be at the $n^{th}$ position to be exact). Did you think I was going to count every element? No but I can count to *any* element using the “same process”. This property turns out to be useful, that is, given a set of elements, I *can* list them down one by one in a way that every element eventually shows up after a finite number of steps. 

Let’s now consider the set of even natural numbers. Is this set countable? It certainly seems so: $2,4,6,…$ Surely, we are not going to miss anything this way. Give me any even natural number and it will show up after finite number of elements. Looks good.

What about the set of all integers? Let us see.

$$
…-3,-2,-1,0,1,2,3,…
$$

Hmmm. Where is the starting point of this listing? Given a integer, say 5, we are hoping it would occur eventually, that is, after a finite number of steps. But this list expands infinitely in both directions! So integers are not countable? But for the integers to be countable, we just need **a** listing that works. We obviously need a starting element. Maybe, start with 0. And?

- Is the listing $0,1,2,…-1,-2,-3,…$ a valid listing (captures our notion of countable) for the set of integers?
    
    Consider some integer -100. Does it occur after some finite number of steps (however large)? No. Any negative integer simply occurs after all the positive integers which are infinite. Therefore this listing doesn’t prove that integers are countable.
    

- Here’s a listing that works for the set of integers
    
    $$
    0,1,-1,2,-2,3,-3,...
    $$
    

# Formalising countability

Little more formally, we say a set is enumerable or countable if its members can be arranged in a single list with a first entry, second entry and so on such that every member of the set occurs sooner or later in the list.

Even more formally, a set $A$ is enumerable if there is a function $f: P \to A$ such that for every $a \in A$, there is some $p \in P$ such that $f(p) = a$. ($f$ is basically a surjection between $P$ and $A$), where $P$ is the set of positive integers.

- Is the list $1,1,2,3,3,4,5,5,6,7,7,8,9,9…$ a proper enumeration of positive integers?
    
    Yes, because every positive integer occurs at some finite position $n$ in the listing. Don’t let the repetitions throw you off!
    

Why is the above definition equivalent to the notion of having a list that lists every element eventually? Suppose we have such a function $f$.  $f$ effectively determines the list. Suppose $A$ were the set of even integers. And let $a$ be some even integer. Then by existence of $f$ we know there is some $p \in P$ such that $f(p) = a$. So, we know $a$ occurs at $p^{th}$ position in the listing defined by $f$.  It’s possible there are multiple choices in $P$ that map to a given $a$. All we know is that there is at least one. So we also know there is a smallest one, since nothing in the set can be smaller than $1$.

Looking the other way, if we have a valid listing, then we can get such an $f$ by simply defining $f$ as follows: $f(p) = a$ where $a$ occurs at the $p^{th}$ position in the given list.

We now see why the two (informal and formal) definitions are the same.  

# Enumerability Gym

Are the following sets enumerable?

- The set of ordered pairs of positive integers.
    
    $(1,1),(1,2),(2,1),(1,3),(2,2),(3,1),(1,4),(2,3),(3,2),(4,1),…$
    
- The set of positive rational numbers.
    
    $1/1, 1/2, 2/1, 1/3, 2/2, 3/1, 1/4, 2/3, 3/2, 4/1, 1/5, 2/4, 3/3, 4/2, 5/1,…$ (similar to the enumeration of ordered pairs of positive integers).
    
- The set of rational numbers.
    
    0, 1/1, -1/1, 1/2, -1/2, 2/1, -2/1, 1/3, -1/3, 2/2, -2/2, 3/1, -3/1,... (similar to the enumeration of integers using enumeration of positive integers).
    
- The set of finite sets of positive integers.
    
    Consider the enumeration: $\{1\}, \{2\}, \{1,1\}, \{3\}, \{1,2\}, \{1,1,1\}, \{4\}, \{1,3\}, \{1,1,2\}, \{1,1,1,1\},…$
    
    First, we list all sets that sum to 1. Next, all such sets that sum to 2. Any finite set of positive integers has some sum n, and will occur at a some finite position in this enumeration. 
    
- Any subset of an enumerable set.
    
    Suppose $A$ is an enumerable set. Let $S \subseteq A$.
    
    Since $A$ is enumerable, there exists a function $f$ from $P$ (set of positive integers) onto $A$. 
    
    We define a partial function $g: P \rightarrow S$ that is onto as follows.
    
    $$
    g(x) = \begin{cases}
      f(x) & f(x) \in S \\
      \text{undefined} & \text{otherwise}
    \end{cases}
    $$
    
    $g$ is surjective because f is surjective. Therefore, any subset of a enumerable set is enumerable.
    
- The union of any two enumerable sets.
    
    Let $A$ and $B$ be two enumerable sets whose enumerations are $a_1, a_2,...$ and $b_1,b_2,...$
    
    Say $C = A \cup B$. Then $a_1, b_1, a_2, b_2,...$ is an enumeration of $C$.
    
- The set of finite strings over a finite or enumerable alphabet of symbols
    
    Suppose $\Sigma = \{a_1, a_2, …\}$ is an enumerable alphabet. Since, $\Sigma$ is enumerable, there is a surjection $f: P \rightarrow \Sigma$.
    
    Define an injection $g: \Sigma \rightarrow P$ as $g(x) = p$ such that $f(p) = x$. We know such $p$ always exists since $f$ is a surjection. 
    
    It follows that $g(x) = g(y)$ implies $x = y$.
    
    Any finite string over $\Sigma$ is a finite sequence $<s_1, s_2, s_3,…s_n>$ which can be encoded as $p_1^{g(s_1)} + p_2^{g(s_2)} + p_3^{g(s_3)} + … + p_n^{g(s_n)}$ where $p_i$ is $i^{th}$ prime. There are infinitely many primes so we will never run out of primes. And every positive integer has a unique prime decomposition. Together, every positive integer corresponds to a unique string and every string corresponds to a unique positive integer. Therefore, the encoding describes a surjection between the set of positive integers to finite strings. 
    

Finally, is a set of all finite subsets of an enumerable set enumerable?