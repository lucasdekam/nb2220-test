(ch:chapter2)=
# Phases of matter and random walks, part I

(sec:Phases_of_matter)=
## Phases of matter

One can distinguish many phases of matter, beyond the standard division
of gas, liquid and solid. For example, solids are called crystalline
when the atoms or components are ordered in a regular, periodic fashion,
and amorphous when there is no regular order. But there are many more
substances that would be difficult to classify as solid, liquid or gas.
These phases of matter are characterized by unique properties. Sometimes
the phase refers to a specific symmetry of their components e.g. in the
case of liquid crystals.

Liquid crystals can have positional order or orientational order, or
both. When there is only orientational order (i.e. the particles are
more or less aligned in the same direction), but no positional order, it
is called a nematic phase. Each type of order is indicated with a
specific name.

Other phases of matter are characterized by their mechanical properties
e.g. gels and foams. Gels and foams tend to behave solid-like, but
deform easily and respond elastically. Foams may also turn into liquids
upon external stress.

Glasses form a class of materials that are "dynamically arrested".
They are usually formed by a rapid process, where the components have no
time to find their optimal position, such that they get trapped in a
frozen, usually amorphous configuration (imagine some radical form of
musical chairs, "stoelendans" in Dutch). This process is appropriately called
"vitrification".

Some phases have specific dimensions, such as membranes (2D) and fibers
(1D). These phases can also be liquid or solid or glassy or liquid
crystalline, or any other combination of properties. There are also
phases characterized by their topology ("vortex matter"), electric
properties (superconductive materials), rheological properties
(superfluids), energetic properties ("active matter" / materials with
molecular motors), and... let us stop here for now.

Try to classify the following phases of matter, and give arguments by
commenting on their properties:

1.   Yogurt
2.   Diamond
3.   The salt ions in vegetable soup
4.   a school of sardines
5.   actin networks
6.   a cell membrane
7.   a sample of proteins after Cryo-EM
8.   skin tissue
9.   a soap bubble
10.  muscle tissue

(sec:particles)=
## Particles

In the 19<sup>th</sup> century the physics community did not believe in
atoms, except the Austrian scientist Ludwig Boltzmann and a handful of
his followers. Even Max Planck had been a strong opponent of the idea,
until much later, when he introduced the word "quantum" and treated
light as consisting of particles (a much more radical and absurd
assumption) based on Boltzmann's ideas.

It may sound absurd now not to believe in atoms, but still, there is no
direct way of observing them. Even with powerful light microscopes, we
cannot see water molecules. Our observation of these particles is all
based on concepts and indirect inference.

Why do you believe in atoms? What is your proof?

(sec:Random_walk_part_I)=
## Random walk, part I

The "random walk" is a famous example of a stochastic process, and it
relates to many different phenomena around us. Einstein used it to
derive that the average position of randomly colliding particles is
described by the diffusion equation. Here is a 1-dimensional version of
a random walk.

A random walker is taking steps left and right with equal probability
(so for every step the random walker takes, there is a probability of
0.5 that the step will be to the right, and 0.5 that it will be to the
left).

1.  What is the mean and standard deviation after one step?
2.  What is the mean and standard deviation after $N=100$ steps? (Hint:
Remember [the exercise](sec:Central_limit_theorem_dice) about the dice, and the
central limit theorem.)
3.   What after $N=10.000$ steps? Argue why diffusion can be a limiting
    process. (in other words, argue why diffusion may not be a very
    efficient process if you want to transport something from $A$ to
    $B$.)
4.   Calculate the probability $P$ that you end up $n$ steps to the right
    of the starting point after $N$ steps, using the central limit
    theorem.
5.   Calculate the same probability $P(n)$, but now exactly. \[hint: you
    would have to do some combinatorics here\] This distribution will be
    indistinguishable from the answer to part (d) for large $N$.

(sec:Association-dissociation_part_I)=
## Association-dissociation equilibrium of a polymer, part I

A long polymer has $N$ sites where certain types of particles can bind.
These particles can bind to each site with equal probability. If a
particle is bound to a site, no other particle can bind to that site.

1.  In how many different ways can one particle bind? (this question was
    intended to be obvious)
2.  In how many different ways can $n$ particles bind, if the particles
    are not identical?
3.  In how many different ways can $n$ particles bind, if the particles
    are all identical? (in more formal language: how many different
    configurations are there for $n$ identical particles?)
4.  For which value of $n$ do you obtain the largest number of different
    configurations?
5.  Draw the number of configurations as a function of $n$, for $N=100$
6.  Does this distribution look familiar? (Can you connect it somehow to
    the previous exercise? If not, no problem.)
7.  Bonus challenge (optional): Can you do this exercise again, but
    assuming that any number of particles can bind to the same site?

These results will be used later.
