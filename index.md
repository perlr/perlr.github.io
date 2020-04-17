---
layout: page
title: About
---

I studied Applied Mathematics at the [University of Magdeburg](https://www.uni-magdeburg.de/en/) and did my studies abroad at [Uppsala University](https://www.uu.se/en), Sweden. My diploma thesis was supervised by [Prof. Klaus Deckelnick](https://www-ian.math.uni-magdeburg.de/home/deckelnick/). 
During my studies I worked as a student research assistent at the [Max-Planck Institute for Dynamics of Complex Technical Systems](https://www.mpi-magdeburg.mpg.de/2316/en), Magdeburg supervised by [Prof. Naim Bajcinca](https://www.mv.uni-kl.de/mec/staff/naim-bajcinca/).

<img align="left" src="/assets/RicardoPerl.jpg" height="205" width="196" img style="float: left; padding-right: 22px;"> 

After that I joined the [Bonn International Graduate School (BIGS) of Mathematics](https://www.bigs-math.uni-bonn.de) at the [Hausdorff Centre for Mathematics](https://www.hcm.uni-bonn.de) in Bonn. I wrote my PhD thesis at the Institute for Numerical Simulation advised by [Prof. Martin Rumpf](https://ins.uni-bonn.de/staff/rumpf) and [Prof. Bert Jüttler](http://www.ag.jku.at) ([JKU](https://www.jku.at) and [RICAM](https://www.ricam.oeaw.ac.at)). During that time I was a member of the project [Geometry+Simulation](http://www.gs.jku.at/) funded by [Austrian (FWF)](https://www.fwf.ac.at) and [German (DFG)](https://www.dfg.de) Science Fund devoted to [Isogeometric Analysis](https://en.wikipedia.org/wiki/Isogeometric_analysis). The topic of my PhD thesis lies in the **intersection of numerical mathematics, computational engineering and graphics**. I developed efficient methods and new algorithms using [subdivision surfaces](https://en.wikipedia.org/wiki/Subdivision_surface).

After finishing my PhD I worked for 4 years at [Continental](https://www.continental.com/en) Tires, Hannover as a **FEM Software Developer** in the **Mechanics and Simulation Development** department focusing mainly on meshing for tires. 

<p align="center">
  <img src="/assets/subdivHands_Eigenmodes.png" height="225"> 
</p>

**My background and interests:**
  - Meshing (esp. quad and hex meshing), finite elements, iso-geometric analysis, computer graphics, computational mechanics
  - Partial differential equations, calculus of variations, numerical methods, high-performance computing, nonlinear problems
  - Differential geometry, geometry processing, Bézier curves, subdivision curves and surfaces, NURBS
  - Software engineering, C++, Qt5/Qml, UX/UI, Swift, OpenGL, Metal    
  - Git, Mercurial, Blender, Paraview, VisualStudio, CMake, QtCreator

<br/>


**PhD Thesis** *"Isogeometric Approximation of Variational Problems for Shells"*


<a href="http://hss.ulb.uni-bonn.de/2016/4359/4359.pdf"><img src="/assets/thesisTeaser.png" height="110%" title="PhD Thesis" alt="PhD Thesis" img style="display: block; margin-left: auto; margin-right: auto; width: 50%; border: 0.2px solid black;" border="1" ></a>

**PhD Defense**  
<a href="./assets/PhD_Defence_Ricardo_Perl.pdf"><img src="/assets/PhD_Defense_Front.png" height="110%" title="Slides PhD Defense" alt="Slides PhD Defense" img style="display: block; margin-left: auto; margin-right: auto; width: 50%;" ></a>

### Isogeometric Analysis with Subdivision Surfaces

Isogeometric surface representations are mostly based on NURBS for quadrilateral meshes resp. box splines as their generalization to arbitrary polygonal meshes. Unfortunately, spline surfaces are restricted to regular grids, so-called patches. There exist two dominating concepts for the construction of smooth surfaces of arbitrary topology. The most common approach in computer-aided design (CAD) for the last decades was to glue many different patches together to form so-called multi-patch spline surfaces. Modeling complex surfaces with multi-patch spline surfaces is time-consuming and complicated, because the gluing has to be done in the right way which requires user interaction. 

Traditionally, subdivision surfaces are widespread in geometry processing and computer graphics in academia as well as in industry and a defacto standard. Subdivision creates surfaces of higher-order smoothness by solving the N-sided hole filling problem. More precisely, the subdivision approach generalizes the subdivision property near regular vertices to vertices of arbitrary connectivity so-called extraordinary vertices. When using the subdivision approach one can select vertices, edges or faces of the control mesh to manipulate the entire shape. Using standard additional split and extrude commands subdivision surfaces combine the power of parametric modeling with the flexibility of direct modeling. This way, the subdivision methodology changed the modeling paradigms in computer-aided design systems over the last years tremendously, see e.g. the Freestyle module of PTC Creo, the PowerSurfacing add-on for SolidWorks or NX RealizeShape of Siemens PLM which employ the subdivision concept. 

The following pictures should highlight their usability in CAGD as well as in simulation.

<p align="center">
  <img src="/assets/subdiv_ball_limit_meshes.png" width="500">  
  <br/>
  Same subdivision surface for different subdivision levels.
</p>

Solving Laplace-Beltrami and bi-Laplacian with given right hand side on different subdivisios surfaces.

<p align="center">
  <img src="/assets/subdivBall1_Laplace.png" width="500">
  <img src="/assets/subdivBall2_Laplace.png" width="500"> 
  <img src="/assets/subdivTorus_Laplace.png" width="500"> 
  <img src="/assets/SubdivHands.png" width="500">
  <br/>
  Left to right: Smooth surface with curved elements; Given right hand side; Solution of Lapace-Beltrami; Solution of bi-Laplcian.
</p>

Based on the developed framework one can easily extend to solve applications such as computation of Eigenfucntions:

<p align="center">
  <img src="/assets/subdivHands_Eigenmodes.png" width="500"> 
  <br/>
  Eigenfunctions (Eigenmodes) of Laplace-Beltrami operator on complex geometry.
</p>

### Gradient flows

Because subdivision surfaces offer a great flexibility in modeling surfaces with C1-smoothness they are ideally suited for the simulation of geometric evolution problems which have many theoretical and practical applications in mathematics, engineering and computer sciences. These evolutions are often based on the gradient flow of an geometric energy. We consider a general type of energies which involve the first and second derivatives of the surface leading to fourth-order partial differential equations for the corresponding Euler-Lagrange equations. For the discretization with standard C0-finite elements, these fourth-order equations have to be split in second-order problems which introduces additional degrees of freedom with possibly no geometric meaning. Furthermore, the splitting has to be performed for each fourth-order problem on its own. We review such a splitting for the case of anisotropic Willmore flow of curves and surfaces and present results for the evolution of curves. As a consequence of the splitting approach one can choose time steps of the size of the spatial grid size. In contrast, the direct, conforming discretization of fourth-order gradient flows with subdivision surfaces only allows time steps of the size of the squared spatial grid size. On the other hand, the discretization with subdivision elements results in a higher order spatial approximation. An effective implicit Euler time discretization would result in a time-error dominated scheme. Therefore, we apply a higher order time discretization based on implicit Runge–Kutta methods to balance the error terms. The crucial characteristic of a gradient flow is that the energy decreases in time. We prove that the energy diminishing property holds in the fully (time and space) discrete setting under mild time step restrictions. We apply the proposed scheme to a variety of geometric gradient flows, such as mean curvature and Willmore flow.


<p align="center">
  <img src="/assets/GradientFlow_Bunny.png" width="900"> 
  <br/>
  Comparison of different geomertic gradient flows to smooth the Stanford Bunny. Left: H1 mean curvature flow; middle: H1 Willmore flow; right: H2 Willmore flow. 
</p>

<br/>

<p align="center">
  <img src="/assets/H2_Willmore_Elch.png" width="600"> 
  <br/>
  A detailed elch flows to a Clifford torus.
</p>

<p align="center">
  <img src="/assets/H2_Willmore_Frog.png" width="600"> 
  <br/>
  A detailed frog flows to a round sphere in only three large time steps.
</p>

### Keyframes: Geodesics, Exponential map and Parallel transport

**Bézier curves** as well as **B-splines and cardinal splines are fundamental tools in computer-aided geometric design**. Applications range from vector graphics to CAD, from computer graphics or animation to computational engineering. All three concepts are linked by the de Casteljau algorithm which is a robust and efficient approach to draw Bézier curves. In Euclidean space, the de Casteljau algorithm constructs polynomials by a weighted recursive combination of straight lines.

We consider the space of shells, where each shell is a point in space. Applying the direct computation of straight lines, Bézier curves and splines to shells as objects in Euclidean space results in many visual problems such as self-penetration of shells. The reason is that the distance of two shells cannot effectively be measured by the Euclidean metric because it does not invoke the inherent structure of shells. Thus, the space of shells is often understood as a Riemannian manifold induced by a Riemannian metric. In the Riemannian setting, **geodesics, i.e. paths of shortest distance**, are the generalizations of straight lines in Euclidean space. Because the geodesic equations require a time stepping method which is usually not robust, Rumpf and Wirth developed the time-discrete geodesic calculus for general shape spaces by introducing a suitable approximation of the squared Riemannian distance. Heeren and co-authors applied the time-discrete geodesic calculus to the space of shells by defining an elastic deformation energy between two shells, which measures membrane and bending contributions. For the numerical implementation they applied a suitable discrete approximation of their previously defined continuous deformation energy using schemes from discrete differential geometry. 

Instead we will discretize their continuous deformation energy with subdivision elements such that we obtain time-discrete geodesics in the subdivision shell space. **With geodesics as generalization of straight lines we define Bézier curves in shape space as a result of a generalized de Casteljau algorithm**. Because the evaluation depends on all input shapes of the Bézier curve, **we construct B-splines in shape space by gluing together piecewise Bézier curves** analogously to the Euclidean setting. Since both approaches do not interpolate all input shapes, we additionally **define cardinal splines in shape space**.

<p align="center">
  <img src="/assets/subdivHands_Geodesics.png" width="600"> 
  <br/>
  Computation of discrete geodesics (green shapes) for given keyframes (In grey: subdivision control meshes).
</p>

<br/>

<p align="center">
  <img src="/assets/GeodesicsAndExponential_Elephant_2.png" width="600"> 
  <img src="/assets/GeodesicsAndExponential_Elephant_1.png" width="600"> 
  <br/>
  Computation of discrete exponental map (pink). After computing a discrete geodesic path we can use the deformation to extend (geodesic shoothing) the last keyframe. 
</p>

<br/>

<p align="center">
  <img src="/assets/ParallelTransport_Cat_Lion.png" width="600"> 
  <br/>
  By combining the concepts of discrete geodesics and geodesic shooting we can tranfer the motion of cat to a lion.
</p>

<br/>

<p align="center">
  <img src="/assets/Quadratic_Bezier_subdiv_Hands.png" width="280" hspace="20"> 
  <img src="/assets/Cubic_Bezier_subdiv_Hands.png" width="380"> 
  <br/>
  Quadratic (left) and cubic (right) Bézier curve in subdivision shape space.
</p>

<br/>

<p align="center">
  <img src="/assets/Quadratic_B-Spline_Hands.png" width="300" hspace="20"> 
  <img src="/assets/Cubic_B-Spline_Hands.png" width="350"> 
  <br/>
  Quadratic (left) and cubic (right) B-spline in subdivision shape space.
</p>

<br/>
<p align="center">
  <img src="/assets/Catmull-Rom_Spline_Hands.png" width="700"> 
  <br/>
  Cardinal (Catmull-Rom) spline in subdivision shape space.
</p>





