---
layout: page
title: Notes
permalink: /notes/
---

Papers that I have not published in any journal, but that I believe is of general interest and worth publishing online.
====

{% for post in site.papers %}
  {% include default.html %}
{% endfor %}

---
### [Geometric derivation of Wigner rotation](/files/notes/wigner_rotation/wigner_rotation_complete.pdf)

Report written in 2018 for PHYS3001 course at Australian National University.

**Abstract**


The [Wigner Rotation](https://en.wikipedia.org/wiki/Wigner_rotation) describes the paradoxical phenomenon in special relativity, where a composition of several [Lorentz boosts](https://en.wikipedia.org/wiki/Lorentz_transformation) could give a pure rotation. Despite having important applications, as well as being an extremely surprising paradox, it is rarely taught in undergraduate physics, and its geometric meaning is rarely mentioned anywhere.

This paper gives an illustrated derivation of Wigner rotation using the geometry of spacetime diagrams, assuming no background in the reader of the geometric style of reasoning about special relativity. This allows Wigner rotation to be easily derived and its geometric meaning understood, allowing it to be taught in an introductory course on special relativity. The [Thomas precession formula](https://en.wikipedia.org/wiki/Thomas_precession) becomes an easy corollary. Illustrative fables and further readings are attached at the end.

<center><img src="/files/notes/wigner_rotation/2_3_lorentz_trans_combined.svg" width="400"></center>

---
### [Hyperbolic dynamical systems, chaos, and Smale’s horseshoe: a guided tour](/files/notes/ergodic_theory/ergodic_theory_project.pdf)

Report written in 2019 for Ergodic Theory course at Australian National University.

**Abstract**

This paper gives an illustrated overview of several areas in dynamical systems. We start with Poincare’s discovery of chaos in the three-body problem, and define the Poincare section method for studying dynamical systems. Then we discuss the long-term behavior of iterating a diffeomorphism in R^n around a fixed point, and obtain the concept of hyperbolicity. Then we give the Arnold cat map as a classical example of hyperbolic map, and prove its hyperbolicity. Then we introduce homoclinic tangles and discover Smale’s horseshoe in it. Then we prove that the behavior of the Smale horseshoe is the same as the binary shift, reducing the problem to symbolic dynamics. We conclude with applications to physics. The target audience is beginning graduate students in mathematics.

---
### [Handout for honours seminar talk on AIXI](/files/notes/2019_honours_seminar_talk/presentation_handout.pdf)

Handout for an undergraduate 25-minute talk in 2019 at Australian National University.
