---
layout: post
title: "A Plan for Pan-Plasma"
tags: ['software', 'fusion', 'code', 'python']
date:   2020-04-01
excerpt: "How the fusion research community can use open-source software to make all their work easier."
---


I have a [software dream](https://twitter.com/TEGNicholasCode/status/1237786892118249474). A dream that the magnetic confinement fusion community can fully embrace the [wonderful ecosystem]() of open-source scientific python packages now available, and bring their scientific workflows into the 21st Century.


## Current problems

Data problems:
- Multi-terabyte datasets
- High-dimensional (gyrokinetics)
- Remotely-stored

Domain problems:
- Warped grids on weird topologies
- Very wide range of different tasks
- Unintuitive units
- Lots of diagnostics
- Simulations upon simulations (e.g. FIDAsim takes transp data)

Management problems:
- Scientists doing the coding
- Repeated effort
- Closed-source
- Outdated tools (IDL)
- Lack of standardization


## Similarity to geosciences

Different to particle physics because data not centralised in some weird domain-specific format (i.e. ROOT)

However, there is one field of science which has created a blueprint for a solution.

- Large multidimensional datasets
- Warped geometries
- Remote data (servers with experimental data or supercomputers with simulation data)


## Pangeo


## Pan-Plasma

We need our own corresponding stack. It can share a lot of the libraries from pangeo.


## Roadmap

Will still need to build some domain-specific libraries though:


### Data structure
  - xarray-based
  - dask-scalable
  - units-aware
  - standardised interface to common formats
  - staggered grids?
  - structure for 
    
    
### Visualisation
  - 2D tokamak plotting libary similar to cartopy
  - Support for physical vessel components in common format (analogous to cartopy's features)
  - Use a modern plotting library like bokeh, or make it plotter-agnostic
  - Holoviews?
  - Also a 3D tokamak plotting library


### Analysis
  - PlasmaPy

### Interface/workflow
  - Shot/simulation dashboard (analogy to tools like panopoly in atmos)
  - Jupyter
  - Bokeh
  - Panel
  - Can be basically all GUI for non-technical experimentalists (like OMFIT aims to)
  
  
## Example workflows

Computational
- Simulation (e.g. BOUT++) data on supercomputer
- Open in-place with dask-backed data structure (similar to xBOUT)
- Visualise for real geometry
- Import machine geometry easily

Experimental
- Pull from CCFE server (or access in-place on freia)
- Diagnostic-specific module to convert data
- Plot lines of sight into device
- Dashboarding for mining shots

Comparison
- Pull both to common format
- Compare

ML?

Bayesian?
- Multiple diagnostics in same format?
- ArViz?


## Other benefits

- Seed interdisciplinary crossover
- Code quality/sustainability
- Staying power - many of these libraries are already actively used/supported by major national labs in geosciences
- Wall off dodgy old tools
- Clear scope makes RSE support easier, professional software practice possible
- Integration with new features e.g. Machine Learning support (sklearn-xarray, pytorch)
- Helps reproducibility
- Save money on MatLab & IDL licenses
- Modularity makes it easier to transfer data and scripts between researchers
- Jupyter-friendly means researchers can more easily see other's work
- Software community for problem-solving (like pangeo's discourse forum)


## Relation to existing projects
- Could replace a lot of OMFIT's internals
- Similar scope to IMAS
- But difference to these is it doesn't worry about running the simulations
