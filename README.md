# Nimrod/O
*NB: This readme is a work in progress adapted from and containing many ancient references from Nimrod/O's 15+ years of life.*

 CONTENTS
1. DESCRIPTION
2. NEW FEATURE SUMMARY
3. TECHNICAL NOTES
4. KNOWN BUGS AND LIMITATIONS
5. LICENSE

---
## 1 DESCRIPTION

Nimrod/O (part of the Nimrod toolkit) allows a user to run an arbitrary computational model as the core of a non-linear optimization process. Nimrod/O allows a user to specify the domain and type of parameters to the model, and also a specification of which output variable is to be minimized or maximized. Accordingly, a user can formulate a question like: what parameter settings will minimize the model output?.

Nimrod/O employs a number of classic built-in optimization algorithms, namely BFGS, Simplex, Divide and Conquer and Simulated Annealing. More recently a variety of novel bi-objective algorithms (Complex, PICS, SFBC) have been added, and two multi-objective algorithms (MOTS2 and NSGA-II) have been integrated. These bi and multi objective capabilities give Nimrod/O the ability to find Pareto optima in two and higher dimensional space.

Jobs can be executed directly on the host platform via the built-in *dispatcher* or farmed out to a variety of platforms, including distributed clusters and computational grid or cloud resources, through Nimrod/G. Nimrod/O has been used for a range of design projects including the optimal design of aerofoils, highly durable mechanical parts and high gain antennas.

---
## 2. NEW FEATURES
The header comments in source/nimrodo/main.c contain a more detailed version changelog.
- Version 3.2 Merged with branch developed by Timos Kipouris which incorporated multiobjective algorithms MOTS2 and NSGAII.
- Version 3.1 allows a search for Pareto optima. In particular it implemented several
novel algorithms: CSC, PICS and SFBC.
- Version 2.9 allows parameters to wrap at the end points, just implemented for the
simplex method.
- Version 2.8 provides for multiple results.
- Version 2.7 provides a mode that just queries the cache.
- Version 2.6 allows a shared persistent cache.

---
## 3. TECHNICAL NOTES

See the Nimrod/O Users' Guide for installation and operation details.

---
## 4. KNOWN BUGS AND LIMITATIONS

Under heavy load (many small tasks) the sockets are swamped and need time to recover. Nimrod/O was never intended for such use, but many users are now applying it for a huge number of concurrent optimizations or for optimization of very simple objectives.

Please file bug reports on the Github issue tracker, contributions welcome!

---
## 5. LICENSE
Nimrod/O is Copyright 1999-2012 Monash University and distributed under Apache License, Version 2.0.

The authors greatfully acknowledge free software libraries bundled with the Nimrod/O source and standard tools which make this possible (too many to list). Users should note in particular that MOTS2 is distributed under the LGPLv3 license, see source/nimrodo/mots2-interface-direct/LICENSE for details.
