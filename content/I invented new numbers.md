Today, I will not teach you some already established yet surprising aspect of math, but rather make you discover some of my own thought process, and how I invented "new numbers". This is not really useful in itself and probably never will be, however I think it is a good illustration of the creative process that has led to actual ground-breaking math discoveries.

I will first explain how the real numbers are defined, then use this to build new numbers. After that, we will explore some of their properties, and go further by taking a look at how we can do the same thing based on other structures than real numbers. Also, I will not prove every claim I make in this article. I will only focus on the demonstrations that help gain an insight. With that said, let’s jump in.

# What are real numbers?

If you’re at least a little used to math, you’ve got a pretty intuitive understanding of what real numbers are. But what’s the definition of these numbers ? Well, it’s not that simple. We know what integers are. We have an easily understandable definition for rational numbers: a rational number is simply an integer divided by a non-zero integer. Even if these integers aren’t coprime, meaning you factor out a number out of them and simplify the fraction, you still got a rational number. And from these rational numbers, we can construct the real numbers which are in a certain way an extension of rational numbers. There are multiple of these definitions, and one of them is with Cauchy sequences.

The definition of a Cauchy sequence is this: a sequence *(a_n)* is Cauchy when

$$
\forall \epsilon > 0, \exists N\in\mathbb N | \forall m,n > N
|a_m-a_n|\leq \epsilon
$$

I can sense that some of you haven’t instantaneously understood, weirdly enough, so let me explain. A sequence is Cauchy if and only if its values become arbitrarily close to each other. For any given distance, there is a certain point from which all values are closer to each other than said distance. For instance, *1/n*

![[1n.png]]

is a Cauchy sequence, *n*

![[n.png]]

is not. And *√n*?

![[sqrtn.png]]

Well, it’s not. Because although consecutive values get closer and closer, *√n* diverges to infinity, so you can’t contain those values in an arbitrarily small zone. And *sin(n)*?

![[sinn.png]]

It doesn’t converge so it’s not Cauchy either, for the same reason. It’s not very hard to show that all convergent sequences are Cauchy. And from these examples, it looks like being convergent and Cauchy are the same thing, right? Well yes, but actually no.

These properties look the same, and there’s definitely a sense in which the values of a Cauchy sequence get arbitrarily close to *something*. It’s indeed the same thing in **R**, which we call a *complete* space for that reason. But it’s not the case for all spaces, as a Cauchy sequence can "converge" towards something that is not in the set. A completely random example is **Q**, the set of rational numbers. *√2* is a famously irrational number, however its decimal expansion (1, 1.4, 1.41, 1.414,...) is a Cauchy sequence in **Q** that does not converge in **Q**, but does in **R**. See where we’re going? 

We would like to define **R** by taking the limits of Cauchy sequences on **Q**. But because the limit in **R** can’t be defined before **R** is, we do so by taking the Cauchy sequences and grouping them. We define an equivalent relation ~ such that two sequences are equivalent if their difference is negligible, a nerdy way of saying it converges to 0. 

$$
(a-n) \sim (a_m) \iff a_n - b_n \rightarrow 0
$$

0 being rational, everything works fine. **R** is thus the set of Cauchy sequences in **Q**, quotiented by the relation ~. It can be seen as the set of the limits of all Cauchy sequences in **Q**.

# Defining our new numbers

So what I did is take a similar reasoning to extend the real numbers. We will use sequences on **R** instead of **Q**. That doesn’t change anything, because any real number has arbitrarily close rational numbers to it (we say **Q** is *dense* in **R**). In that case, all Cauchy sequences are convergent and vice versa, so using them wouldn’t be very interesting. Instead, we will loosen the requirements and take bounded sequences instead, which is a way broader set because convergent implies bounded. We thus have a way broader set. You may wonder why we took bounded sequences only and not all sequences, and that’s for a good reason we will see shortly after.

$$
\mathbb H= \{{\text{bounded sequences in }\mathbb R}\}/\sim
$$

Let's call this set **H**, for hypernumbers. Also, we can call the limit of any bounded sequence the hypernumber corresponding to the equiv class of the sequence. This is completely legal because it extends the definition of the limit to all bounded sequences, not just convergent ones. **H** can then be seen as the set of the limits of all bounded sequences in **R**.

# Properties

So we just defined a set. But we would like to call it a space, aka a set with extra properties, such as internal operations. We will do so by extending the properties of real numbers seen as limits of sequences.

The simplest structure we can give to this set, is that of a vector space, meaning you can add, subtract and multiply any element by a scalar (a real number) and the result is still in **H**. For *a* and *b* in **H** you can just take bounded sequences *(a_n)* and *(b_n)* whose limits are *a* and *b*, *a+b* is the limit of *(a_n+b_n)*. For instance, let's take the limit of *(-1)^n* let’s just call *u*, and *1 = lim 1* which is also a plain old real number, we have 

$$
u+1 = lim (-1)^n+1
$$

And of course it doesn’t matter which sequence you pick, because they only differ by something negligible, so the possible sums will too.

In the same way, we can define scalar multiplication by multiplying the associated sequences. 

$$
2u = lim 2(-1)^n
$$

It doesn’t matter which sequence you pick because a scalar times something negligible is still negligible. And the neutral element is 0.

We just made **H** into a vector space, how neat? But we can do more. We can also define a product in the same way. *ab* is the limit of *(a_n)(b_n)*. But this time it’s a bit trickier to make sure everything works fine regardless of the sequences you pick, so let’s do a proper demonstration. We still have our *a* and *b* being the limits of *(a_n)* and *(b_n)*. Let’s pick any other sequences representing *a* and *b*, that we can write

$$
(a_n)+o(1) 
$$

And

$$
(b_n)+o(1)
$$

With *o(1)* meaning something negligible, and try to show that *(a_n)(b_n)* has the same limit as this guy. In that case, we develop the product and get this

$$
(a_n+o(1))(b_n+o(1)) = a_nb_n + a_n o(1) + b_n o(1) + o(1)
$$

By taking the limit, we see that we’re left with *ab* and those guys, we would really like to converge to 0. But remember when we said that all those sequences are bounded? That’s right, a bounded sequence times a negligible sequence is still negligible. So we’ve just shown that the product between two hypernumbers can be defined without any problem. **H** is then not only a vector space, but an *algebra* with the identity element being 1, the limit of the sequence *(1)*.

So, can we divide by hypernumbers? Before we answer this question and explore more properties, we need to talk about eigenvalues. Each hypernumber has a set of specific real values that dictate its properties. This stems from the fact that all bounded sequences have what we call *adherent* values. An adherent value of a sequence is a number which a subsequence converges to. For instance, this guy 

(-1)^n

Has -1 and 1 as adherent values. And *sin* actually has the whole line segment [-1,1]. Also, because sequences converging to a hypernumber only differ by something that converges to 0, the subsequences have the same limits, so those adherent values are the same. Meaning they only depend on the hypernumber. Those who are familiar with linear algebra might be wondering why I chose to call them eigenvalues, and you will see that they share similar properties to those of matrices. Let’s also call the set of eigenvalues the spectrum, noted *sp*.

To get back to divisibility in **H**, we can check if a hypernumber is invertible based on its eigenvalues. And just like with matrices, a hypernumber is invertible if and only if 0 is not an eigenvalue of it. That’s because if 0 is an eigenvalue, all associated sequences have a subsequence that converges to 0. So the inverse would need to have sequences with subsequences that go to infinity, and thus not be bounded.

An additional property has to do with polynomials. If a polynomial evaluated on a hypernumber is 0, then the eigenvalues of the hypernumber are contained in the polynomial’s zeros. Note that the opposite isn’t always true, because you can add any non-eigenvalue zero to a polynomial by multiplying it by another polynomial. For instance,

$$
u^2 = 1
$$

So

$$
u^2 -1 = 0
$$

And the eigenvalues -1 and 1 of *u* are indeed zeros of the polynomial *x^2-1*. However not all hypernumbers have such polynomials.

We can also use those eigenvalues to define a norm, aka a distance to zero. The norm of a hypernumber is the greatest absolute value of its eigenvalues. This simple definition validates all conditions to be a norm:

- Homogeneity: for any scalar *lambda* and hypernumber *x*, |lambda x|=|lambda||x|
- Separation: *|x| = 0* if and only if *x=0*
- The triangle inequality: *|x+y|<=|x|+|y|*

And finally, we can define an order. We say that *x* is bigger than *y* if all eigenvalues of *x-y* are greater than 0. The only caveat is that this order is partial, meaning that not all hypernumbers can be compared to each other.

# **H** of other vector spaces

So that’s it for our hypernumbers, which are an extension of the real numbers. But what if we use the same construction on other vector spaces ? Actually, things still work out. You can for instance take **H**(**C**), and end up with the complex hypernumbers. **H**(**C**) still has all properties **H**(**R**) has, except for the partial order thing. But that’s only because complex numbers in general can’t be ordered. You can also build **H** over sets with less properties, like vectors for instance. And of course, the properties of **H**(**E**) depends of those of **E**. Hell, you can build **H** over something that's not even a vector space.

# Conclusion

So, let's sum up what we have done. We built a new algebraic structure over **R**, discovered some interesting properties, and then thought about building it over other types of structures. I could have given even more details and specific properties, but that's not really the point of the article, and I highly encourage you to try and explore it by yourself.

You might want to ask me "why did you call those numbers? according to their original definition, they're just classes of sequences, nothing to do with numbers!" And in fact, you're right. But remember that real numbers can be defined the same way. Actually, it doesn't really matter how we call them, or the exact definition given to them. What's really important is the structure it has, the way numbers and in our case hypernumbers behave. If it looks like a duck and quacks like a duck, it's isomorphic to a duck, and that's what's really interesting.

Will that ever be useful in math? Probably not. However I think it's the process that's really interesting. Some pretty smart guy somewhat extended the rational numbers into the real numbers, and we extended this extension to create a new structure of our own. And it's precisely that way of thinking outside the box, of trying to generalize concepts outside of their original realm and see which properties are kept or added, that leads to progress in math. 

That's how we discovered complex numbers, by expanding the plain old real numbers. We lose some properties and gain some. Heck, even integers are a generalization of natural numbers. And some functions used in important parts of physics or cryptography like the gamma function or Riemann's zeta function are generalizations to the complex plane of simpler functions. These are specific examples, but by thinking about it you'll realize that most mathematical concepts originated the same way: we take something we already know and ask ourselves: what if? So, who said math isn’t creative?
