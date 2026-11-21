# RHEED pattern simulator

An interactive, browser-based simulator of reflection high-energy electron diffraction (RHEED) patterns, from the [FerroThinFilms Lab](https://xiaoshanxu.unl.edu/) at the University of Nebraska–Lincoln.

**Use it online: https://xiaoshanxu.github.io/RHEED-simulator/**

It runs entirely in your browser (desktop or phone), with no installation, no server and no data upload.

## What it does

The simulator builds the kinematic Ewald construction for a 2D surface lattice and shows the result in two linked views:

- **Screen pattern:** the diffraction spots on a flat phosphor screen, with the specular (0,0) spot highlighted and the shadow edge marked.
- **3D Ewald construction:** the Ewald sphere, reciprocal-lattice rods, rod/sphere intersections, diffracted beams, incident beam and screen plane. Drag to rotate.

Both views update as you move the sliders.

## Parameters

| Parameter | Description |
|---|---|
| Beam energy | Electron energy in keV |
| Incidence angle | Grazing angle of the beam to the surface, in degrees |
| Azimuth | Rotation of the lattice about the surface normal, in degrees |
| a, b | Real-space lattice constants, in Å |
| γ | Angle between a and b, in degrees |
| Max rod order | Largest index of the reciprocal-lattice rods included |
| Lattice preset | Square (b = a, γ = 90°) or hexagonal (b = a, γ = 120°) |

At azimuth 0, the real-space vector **a** lies along the beam, and **b** is at angle γ from **a**.

## Model

The incident wavevector has magnitude k = √(2mE)/ħ and makes the angle θ₀ with the surface. The surface lattice gives reciprocal-lattice rods perpendicular to the surface at in-plane positions G = n₁a* + n₂b*. Elastic scattering requires the outgoing wavevector to lie on the Ewald sphere of radius k, so every rod that cuts the sphere gives one diffracted beam. The beam direction (kx, ky, kz) is projected onto the screen plane x = 1.5 k, giving the spot position (y, z) = (1.5 k·ky/kx, 1.5 k·kz/kx). The screen distance only rescales the pattern. Spot size follows sin(θ₀)/sin(Θ/2), where Θ is the angle between the incident and diffracted beams; this is a qualitative weighting, not a calculated intensity.

## Limitations

This is a kinematic, qualitative tool.

- The rods are infinitely thin, so there is no streaking from finite domain size, roughness or film thickness.
- There are no Kikuchi lines, no inner-potential refraction and no dynamical effects, so spot intensities are only indicative.
- The wavelength is non-relativistic, which changes k by roughly 1% at 20 keV.
- The screen is flat and perpendicular to the in-plane beam direction.

## Run locally

The whole tool is a single file, `index.html`. Download it and open it in any modern web browser.

## Citation

If you use this tool in a publication or presentation, please cite it, for example:

> Xu, X., FerroThinFilms Lab, University of Nebraska–Lincoln. RHEED pattern simulator (2026). https://xiaoshanxu.github.io/RHEED-simulator/

## License

Released under the MIT License. See the `LICENSE` file.

## Contact

Questions and bug reports: please open an issue in this repository or see the [group website](https://xiaoshanxu.unl.edu/).

© 2026 FerroThinFilms Lab, Department of Physics and Astronomy, University of Nebraska–Lincoln.
