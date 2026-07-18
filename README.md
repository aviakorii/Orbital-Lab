# Orbital Lab

Orbital Lab is a web-based Three.js solar system workspace. The first module
renders the Sun and eight planets, calculates date-aware heliocentric positions,
and provides object inspection, timeline playback, orbit visibility, camera
focus, and display-spacing controls.

## Scientific model

- Planet positions use NASA/JPL's approximate Keplerian elements and rates for
  the J2000 ecliptic, valid from 1800 through 2050.
- Kepler's equation is solved iteratively in `lib/orbital-mechanics.ts`.
- Distances shown in the inspector remain physical AU values. The 3D view uses
  logarithmically compressed distance and exaggerated planet radii so all eight
  planets remain visible.
- The habitability index is an explicitly labeled educational heuristic, not a
  NASA statistic or a probability that life exists.

Primary references:

- [JPL approximate planetary positions](https://ssd.jpl.nasa.gov/planets/approx_pos.html)
- [JPL planetary orbits and ephemerides](https://ssd.jpl.nasa.gov/planets/orbits.html)
- [NASA solar system facts](https://science.nasa.gov/solar-system/solar-system-facts/)
- [NASA orbits and Kepler's laws](https://science.nasa.gov/solar-system/orbits-and-keplers-laws/)

## Project shape

- `components/solar-system`: Three.js scene and workspace controls
- `contexts`: typed simulation state
- `data`: local planet and orbital-element dataset
- `lib`: orbital calculations and display transforms
- `types`: shared domain types

## Run locally

Requires Node.js 22.13 or newer.

```bash
npm install
npm run dev
```

Use `npm run build` for a production build and `npm test` for the build plus
rendered-workspace checks.
