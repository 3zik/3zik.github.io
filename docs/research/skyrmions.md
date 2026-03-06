# Micromagnetic Simulation of Magnetic Skyrmions in Multilayer Systems

Magnetic skyrmions are nanoscale, topologically protected spin textures that arise in certain magnetic materials. Because of their stability, small size, and ability to be manipulated by external stimuli such as magnetic fields or electric currents, skyrmions are promising candidates for next-generation spintronic devices, including high-density memory and logic technologies.

A defining feature of skyrmions is their **topological charge** (also called the *topological winding number*), \( Q \), which characterizes the global structure of the spin configuration and contributes to its stability. For example, a bubble skyrmion with a core of spins pointing upward that gradually transition to spins pointing downward has a topological charge of \( Q = 1 \), while the reverse configuration corresponds to \( Q = -1 \).

My research investigates the behavior of skyrmions in multilayer magnetic systems using micromagnetic simulation techniques. In particular, I study **antiferromagnetically coupled skyrmions** that form in layered materials composed of alternating magnetic elements. These systems can host paired skyrmion structures whose interactions lead to unusual magnetic dynamics and enhanced stability. In an antiferromagnetically coupled skyrmion pair, the individual skyrmions in adjacent layers have opposite topological charge, giving the combined structure an effective charge of \( Q = 0 \). As a result, these systems suppress effects such as the **Skyrmion Hall Effect**, where skyrmions driven by electrical currents deflect sideways due to their topology. Reducing this transverse motion makes antiferromagnetically coupled skyrmions promising candidates for stable skyrmion-based spintronic devices.

To study these phenomena, I develop large-scale micromagnetic models using the GPU-accelerated simulation framework **MuMax³**, which allows efficient simulation of nanoscale magnetic systems. These simulations model the spin configurations of multilayer materials and allow us to investigate how skyrmions evolve under applied magnetic fields and other external perturbations. By comparing simulated magnetization textures with experimental imaging results, this work helps identify the mechanisms that control skyrmion size, stability, and field-driven dynamics.

This research contributes to a broader effort to understand how topological magnetic structures behave in engineered materials and how they may be controlled for future information technologies. Beyond classical spintronics applications, theoretical work by **Naoto Nagaosa** and **Yoshinori Tokura** has also proposed that skyrmions could potentially serve as platforms for quantum information processing, including possible realizations of topologically robust qubits.

## Presentations

**Furman, E., Kirk, A., Hou, Y., Carroll, T., Buchanan, K., Cheng, X. M. (2025).**  
*Micromagnetic Simulations of Field-Driven Antiferromagnetically Coupled Skyrmion Pairs.*  
Poster presented at the SSR Poster Session, Bryn Mawr College. Also presented at the Quantum Day Conference (Haverford College) and the Haverford College KINSC Research Symposium.

**Furman, E. (2025).**  
*Micromagnetic Simulations of Field-Driven Antiferromagnetically-Coupled Skyrmions.*  
Talk presented at the Physics Research Symposium, Bryn Mawr College.

**Furman, E. (2026).**  
*Micromagnetic Simulations of Field-Driven Antiferromagnetically-Coupled Skyrmions.*  
Abstract accepted for an undergraduate oral presentation at the APS March Meeting.

## Abstract (APS March Meeting 2026)

Magnetic skyrmions are chiral spin textures with potential applications in spintronic devices and quantum computing. The discovery of a topological spin memory effect in Co/Gd/Pt multilayers demonstrated the robust topological protection of antiferromagnetically coupled skyrmion pairs. In this work, micromagnetic simulations are used to study the evolution of spin configurations in multilayer systems under applied magnetic fields. A multilayer model was constructed in MuMax³ to simulate the magnetic behavior of the system, allowing layer-resolved magnetization maps to be analyzed. The simulations reveal antiferromagnetic coupling between adjacent layers and reproduce experimentally observed changes in skyrmion size following pulsed magnetic fields. These results help clarify the mechanisms governing field-driven dynamics of antiferromagnetically coupled skyrmions.

*Work supported by NSF ExpandQISE (#2427091).*