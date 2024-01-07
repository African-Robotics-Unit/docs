![Mechatronics Lab Logo](http://www.mechatronics.uct.ac.za/sites/default/files/mechatronics_logo_color_0.png)


# Links to resources
Searching for information online is often either overwhelming (too many resources, and you don't know what's good) or underwhelming when little to nothing comes up. Hopefully putting links to all the good stuff in this document will make finding knowledge a bit easier.

Contents:

- [Trajectory optimization](#trajectory-optimization)
- [Differential equations](#differential-equations)
- [Robotics / Nonlinear control](#roboticsnonlinear-control)
- [Linear algebra](#linear-algebra)
- [Mechanics (Newtonian, Lagrangian)](#mechanics-newtonian-lagrangian)
- [Computer vision](#computer-vision)
- [Kalman Filtering](#kalman-filtering)
- [Modelling and simulation using `SymPy`](#modelling-and-simulation-using-sympy)
- [Computer Vision](#computer-vision)
- [Lab Databases](#lab-databases)
- [Git](#git)

Original version from [LiamClarkZA/mechatronics-lab](https://github.com/LiamClarkZA/mechatronics-lab)

---

## <a name="lab-databases"/> Lab Databases
The Lab has online resources. Some of these are resources based on an online server. These can be found by loging into the UCT VPN. Following that, 
go to [Mechatronics-Nas](http://mechatronics-nas.uct.ac.za). The username is 'amir' and the password is 'workonly'.
You can also find UCT's licensed software at this [website](http://mecnas.uct.ac.za/software/). You will need to be on the UCT VPN to access the site. 
You can find and install the VPN through [ICTS](http://www.icts.uct.ac.za/VPN).


## <a name="trajectory-optimization"/> Trajectory optimization 
Stacey has written [a series of tutorials](https://github.com/UCTMechatronics/pyomo_tutorials) on trajectory optimisation using PyOmo, a Python library

[Matthew Kelly's website](http://www.matthewpeterkelly.com/index.html) has some great great intro links for trajectory optimization. A good place to start would be his [video tutorial](https://www.youtube.com/watch?v=wlkRYMVUZTs)

If you want to get a deeper understanding of how nonlinear optimizers actually work, consider reading John T. Bett's [Practical Methods for Optimal Control and Estimation Using Nonlinear Programming](https://epubs.siam.org/doi/book/10.1137/1.9780898718577). From the link: "The book describes describes how sparse optimization methods can be combined with discretization techniques for differential-algebraic equations and used to solve optimal control and estimation problems." It isn't too math-y and builds up most ideas from scratch, but may take a long time to get through


## <a name="differential-equations"/> Differential equations
A good resource to start getting a better understanding of differential equations would be 3Blue1Brown's series of videos on [differential equations](https://www.youtube.com/playlist?list=PLZHQObOWTQDNPOjrT6KVlfJuKtYTftqH6)


## <a name="roboticsnonlinear-control"/> Robotics / Nonlinear control
Russ Tedrake's [underactuated robotics course](http://underactuated.csail.mit.edu/underactuated.html) covers a wide range of tools useful for controlling underactuated systems (ie robots). Look at the contents of the free textbook to get an idea of what's covered. The programming is done in python and there's a free online textbook


## <a name="linear-algebra"/> Linear algebra
Prof. Gilbert Strang's [Linear Algebra course](https://ocw.mit.edu/courses/mathematics/18-06sc-linear-algebra-fall-2011/index.htm) is a good introduction/refresher to linear algebra. It has video lectures and summarized lecture notes

MathTheBeautiful's videos on [linear algebra](https://www.youtube.com/playlist?list=PLlXfTHzgMRULZfrNCrrJ7xDcTjGr633mm) go from high school level all the way to orthogonal/Legendre polynomials, polynomial bases, QR decomposition, Gaussian quadrature, LDU/LDLT decomposition, etc and his videos are fun to watch


## <a name="mechanics-newtonian-lagrangian"/> Mechanics (Newtonian, Lagrangian)
Prof. Vandiver's [introduction to Lagrange with examples](https://ocw.mit.edu/courses/mechanical-engineering/2-003sc-engineering-dynamics-fall-2011/lagrange-equations/lecture-15-introduction-to-lagrange-with-examples/) lecture "introduces Lagrange, going over generalized coordinate definitions, what it means to be complete, independent and holonomic, and some example problems"

The answers to [this question](https://www.quora.com/What-is-the-comparison-among-Newtonian-Lagrangian-Hamiltonian-and-quantum-mechanics) on Quora are also quite good introductions/recaps of the concepts of Newtonian, Lagrangian and Hamiltonian mechanics.


## <a name="kalman-filtering"/> Kalman Filtering
[Kalman-and-Bayesian-Filters-in-Python](https://github.com/rlabbe/Kalman-and-Bayesian-Filters-in-Python) is an amazing resource to learn about Kalman Filtering and Bayesian stats in general. It uses Python and a series of Jupyter Notebooks.

[This guide](https://home.wlu.edu/~levys/kalman_tutorial/) builds the intuition of the Kalman Filter from the ground up, assuming very little knowledge from the reader.

[This article](https://www.bzarg.com/p/how-a-kalman-filter-works-in-pictures/) by the bzarg blog is better as a second resource, which visualizes everything.


## <a name="modelling-and-simulation-using-sympy"/> Modelling and simulation using `SymPy`
[This tutorial-style talk](https://www.youtube.com/watch?v=r4piIKV4sDw) teaches you "how to derive, simulate, control, and visualize the motion of a multibody dynamic system with Python tools"

[Blender](https://www.blender.org/) is a de facto standard of 3D modelling software for biomechanics, which is also controlled by Python.
[Donut Tutorial](https://www.youtube.com/playlist?list=PLjEaoINr3zgEPv5y--4MKpciLaoQYZB1Z) is one of the best tutorials for the beginners.

[3D Slicer](https://www.slicer.org/) can analyse Computed Tomography (CT) data with [SlicerMorph](https://slicermorph.github.io/) plugin.


## <a name="computer-vision"/> Computer Vision
[Daniel Cremer's Videos](https://www.youtube.com/watch?v=RDkwklFGMfo) will give you a good overview of multi-view camera work. 

[First Principals of Computer Vision](https://www.youtube.com/channel/UCf0WB91t8Ky6AuYcQV0CcLw) YouTube channel is a good resource for explaining concepts visually and also goes into the math.

[CVonline](http://homepages.inf.ed.ac.uk/rbf/CVonline/) is good for finding links for specific topics

[Hartley & Zisserman](https://www.cambridge.org/core/books/multiple-view-geometry-in-computer-vision/0B6F289C78B2B23F596CAA76D3D43F7A) is an excellent (though math heavy) textbook.

[OpenCV documentation](https://docs.opencv.org/3.4/dc/dbb/tutorial_py_calibration.html) is also quite informative with nice diagrams to explain how the code works


## <a name="git"/> Git 
[Atlassian's tutorials](https://www.atlassian.com/git/tutorials) are a fantastic and easy-to-follow set of git guides from beginner to ```git-ninja```

[Installing git](https://www.atlassian.com/git/tutorials/install-git)

[Sourcetree](https://www.sourcetreeapp.com/) is a great free GUI if you'd prefer that to using the command line

[gitignore.io](https://gitignore.io) is a really nifty tool that will build a sample .gitignore file for you so you don't have to!

[git-flow](https://danielkummer.github.io/git-flow-cheatsheet/) is a library which simplifies the git process and follows the git flow branching methodology. The library isn't essential, but the methodology is highly recommended!
