SESM3032 Coursework
Heat Conduction Modelling and Optimisation with COMSOL
Objectives
Apply FEM modelling workfow to build and solve COMSOL models for heat conduction prob-
lems of complex geometries.
Use symmetry where appropriate for model simplifcation and faster computation.
Extract, present, and interpret modelling results for analysis, discussion, and comparison with
analytical results given in lectures.
Optimise fin and heat-sink designs to meet given specifcations and outline strategies to manage
operations above the nominal heat load.

Report
 The coursework text should be written as lab report rather than an essay. It should include a
short introduction at the beginning and conclusions at the end. The report should cover all of
the modelling tasks A1-A9 and B1-B7 detailed below
 COMSOL models used should be presented in sufficient details to include the geometries, material
properties, boundary conditions, meshing.
 Justifications for the choices of material, heat transfer, and geometric parameters should be
included and used for qualitative estimate where possible
 The methods/formulae for derived quantities, such as total heat transferred Q, fin effectiveness
εf , and fin efficiency ηf , should be given in terms of functions/operations of modelling results
 Discussions and comments on the modelling results are essential. A collection of graphs/figures
without explanation/interpretation is insufficient
 No limit on words count or length

Coursework Part A: Radial Fin Modelling and Optimisation (40%)
Figure 1: Radial fin illustration
Use COMSOL to model a radial fin with a rectangular
profile area Ap = (r2 − r1)d where d is the fin thickness,
r1 the inner radius at the fin root, and r2 the outer radius
at the fin tip. The fin operates at root temperature Tb
for heat transfer by convection with an environment at
temperature T∞. The tube itself does not have to be
a part of the model when Tb is set on the tube's outer
surface. Carry out the following modelling tasks:
 Build COMSOL Model
A1 Use appropriate dimensionality and symmetry to create a flat radial fin that has fixed temperature Tb at the root and is cooled down by
convection with an environment at surrounding temperature T∞. Define the following pa-
rameters: root temperature Tb, fluid temperature T∞, convective heat transfer coefficient
h, fin thermal conductivity k, fin profile area Ap, fin inner and outer radius r1 and r2 re-
spectively, and fin thickness d. Justify the values chosen for the parameters and make sure
Tb and T∞ are sufficiently different for a meaningful heat transfer.
 Solution and Analysis
A2 Calculate the steady state solution for the values assigned above to the parameters. Plot
the fin temperature profile along the radial direction. For comparison in the same graph,
also plot the analytical temperature profile of a plate fin of the same thickness and length.
Comments on their similarities and differences and offer your explanations.
A3 Use the solution to calculate the fin heat transferred Qf , fin effectiveness εf , and fin efficiency
ηf ; compare the values with those of obtained with the radial n eciency chart ηf (Fp)
provided in the handout (slides 93-94).
A4 Comment on the performance of your initial fin design and discuss the scopes for enhance-
ment or downscaling. Adjust the geometric design and material selection until, in your
judgement, the results are satisfactory and representative for an effective fin.
 Optimisation
A5 Model by parametric sweep to obtain and plot the fin heat transfer Qf as a function of the
fin thickness d, which is swept while the fin length varies accordingly with the inner radius
r1 and the profile area Ap remain constant as initially assigned. Calculate and plot the
corresponding fin effciency ηf as a function of d. Find the optimal fin thickness dopt and
the corresponding optimal fin length for the maximum Qf . Comments on the practicality
and manufacturability of the optimal fin geometry.
A6 Model by parametric sweep to obtain and plot ηf as a function of the fin parameter Fp. Use
the fin thickness d as the sweeping parameter while for the fin length varies accordingly with
maintaining (r2 + d/2) = 2r1 and Ap constant. Compare the results with that provided in
the handout (slides 93-94) for flat radial fins. Repeat the sweep for (r2 + d/2) = 1.5r1 and
(r2 + d/2) = 3r1 for further comparison.
 Radial Fin Array
A7 Build a simple heat exchanger model of an array of 11 radial fins evenly spaced along a
length of tube of the same material as the fins. Assign a sensible tube thickness relative to
r1 and define the tube length as an additional parameter.
A8 Model the heat exchanger for condensing saturate steam at 1atm insider the tube by cooling
air at T∞ = 20oC flowing outside over the fin and the tube with same heat transfer coeffcient
h used for the fin optimisation at the assigned profile area Ap.
A9 Calculate and plot the temperature distribution along the tube and fin for the optimal fin
design and 3 different tube lengths. Discuss the characteristics of the temperature profile
and explain the changes according to the tube length. Calculate the corresponding water
condensation rates achieved.
Coursework Part B: Design and Modelling a Pin-fin Array Heat-sink for CPU Cooling (60%)
Figure 2: A pin-fin array heat-sink
With the increasing level of integrations in modern electronics,
their power consumption per components has been also increas-
ing. State-of-the-art CPUs have heat flux in excess of heat flux
of 100Wcm−2. A typical heat-sink with pin-fin arrays for CPU
cooling consists of a collection of pin-fins attached at root to a
flat copper disc which is known as the heat spreader for direct
contact with the CPU chip (see figure on the right). Complete
the following design and modelling tasks:
B1 Use Newton's law of cooling to determine the required heat transfer coefficient by air at T∞ =
20oC for direct convection cooling of the chip area of 3.5mm radius for a CPU heat loads maximum
of 50W at maximum CPU temperature of TS = 70oC. Calculate the CPU temperatures at lower
heat loads of 0.5W and 5W. Repeat the calculations for a round heat spreader of a radius 30mm.
Explain why results justify the need for a heat-sink with further extended surfaces.
B2 Use COMSOL (similar to A5 above) to obtain the optimal cylindrical pin-fin design (radius
and length) for a fxed fin volume Vf , fin thermal conductivity k, and a realistic heat transfer
coefficient h for natural convection by air. Justify the choices for fin material, fin volume 50 ≤
Vf ≤ 200 mm3, and air heat transfer coefficient h. Plot Qf as a function of fin radius to show the
optimal heat transfer obtained for a root temperature Tv = 65oC and air temperature T∞ = 20oC.
Estimate the number of pin-fins required for the pin-fin array heat-sink for a maximum CPU
heat lead of 50W.
B3 Build a 3D model to include the round heat spreader and with an array of your optimal cylindrical
pin-fins distributed in pattern of your choice. The heat spreader should have a radius R ≤ 30mm
and have an appropriate thickness δ. The exposed lower surface of the spreader is considered
adiabatic except for a boundary condition of given heat flux q = Q/ACPU where the spreader is
attached to the CPU die. The spreader upper surface and the fin surfaces should be subjected to
a convective boundary condition with the heat transfer coefficient h given in B2 and the ambient
at T∞ = 20oC. It's important to use symmetry of pin-fin distribution and appropriate meshing
to ensure a manageable COMSOL model for your PC.
B4 Obtain steady state solutions for your design for several heat loads levels of Q ∈ [0.5, 50] W.
Identify and explain location for the maximum temperature Tmax, then plot Tmax as a function
of Q. Adjust the spreader thickness δ for sufficient robustness and a good compromise between
the thermal resistances along and across the spreader.
B5 For a Tmax significantly above or below 70oC, increase or decrease the number of pin-fins accord-
ingly. In case of a very high Tmax, consider if the heat transfer coefficient might be increased
with justification.
B6 For the Q = 50W, obtained the transient behaviour of the heat-sink desgin finalised in B5. with
the geometry found in B5 and an initial condition of Ti = 20oC. Determine the time required
for Tmax to reach 68oC.
B7 Model the transient behaviour at a higher heat load, e.g., an overclocked CPU with Q = 65W
and explain how to used the result for devising a throttling scheme for a minimal impact on the
computation speed. Propose a dynamic heat load profile to sustain the CPU performance as
high as possible. Solve the transient problem with the proposed dynamic load profile instead of
a constant heat load.
