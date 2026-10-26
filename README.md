# 07 Smoke Trace

**▶ Play it:** https://hanji-xu.github.io/smoke-trace/

**Observation:** a smoke trail is a data visualization of air movement, aggregated over time. Smoke from a fixed source is a *streakline*: the record of every air parcel that has passed through the source.

**What it does:** a real-time 2D fluid simulation on the GPU (WebGL2) in SI units at 1:1 real time. The air is simulated. Smoke, heat and lines are ways of looking at it.

- **Source:** incense, a candle (nearly smokeless, which is real; choose Heat to see its plume), a blown-out candle (the smouldering wick's wisp), or incense and candle together.
- **Air:** a still room, a steady breeze, gusts, or a waving hand. You can also drag on the smoke to wave your own hand through it.
- **Show:** smoke, streaklines, pathlines, streamlines, all three lines, air arrows (each arrow shows where the air gets in 0.1 s), or heat. In steady air the three line types coincide. In changing air they come apart.
- **How it works:** a second page with a chart of the candle plume against plume theory, plus the numbers, equations, constants, method, estimates and sources.

**Physics:** incompressible Navier–Stokes with Boussinesq buoyancy (g·ΔT/T₀), heat advection and diffusion, and passive smoke. Stable fluids with MacCormack advection, a multigrid pressure solve, explicit viscosity (ν = 1.5×10⁻⁵ m²/s), and thermal diffusion (α = 2.2×10⁻⁵ m²/s). The air is computed above the visible ceiling and past both sides of the screen, so rising smoke leaves the room. Checks:

- The candle plume runs 0.94 / 0.99 / 0.58 m/s at 20 / 30 / 45 cm, against 1.17 / 0.94 / 0.78 m/s from Morton–Taylor–Turner plume theory for 60 W.
- Still-room air stays at 3–4 cm/s over a 60 s run with both sources lit.

**Flagged:** source strengths (★ estimates), and the 2D slice: sources act as line sources and the hand as a bar. Room-temperature air settles back to rest with a 2 s time constant, standing in for the 3D eddy break-up that a flat slice lacks. Numerical diffusion is well above air's viscosity, and Boussinesq is applied near the flame. All of this is listed under **How it works**.

One HTML file with no libraries. It loads the Newsreader web font and falls back to Georgia offline. Needs WebGL2 with float render targets (any recent desktop or phone browser).

---

Part of **Art Insights**, a series of interactive pieces by Hanji Xu. Open `index.html` in a current browser. See also [01 Stubble Field](https://github.com/Hanji-Xu/stubble-vector-field) and [X Stream](https://hanji-xu.github.io/x-stream/).
