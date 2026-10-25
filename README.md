# 07 Smoke Trace

**Observation:** a smoke trail is a data visualization of air movement, aggregated over time. Smoke from a fixed source is a *streakline*: the record of every air parcel that has passed through the source.

**What it does:** a real-time 2D fluid simulation on the GPU (WebGL2) in SI units at 1:1 real time. The air is simulated; smoke, heat, and lines are ways of looking at it.

- **Visualize:** smoke density, excess temperature (heat), raw velocity vectors (arrow = distance travelled in 0.1 s), streaklines, pathlines, streamlines from seeds, and a whole-field streamline map. In steady flow the three line types coincide. In unsteady flow they split apart.
- **Sources:** a burning candle (nearly smokeless, which is real; turn on Heat to see its plume), a snuffed candle (the smouldering wick's wisp), an incense stick, your hand (drag), an automatic hand wave, a breeze with gusts, and a room draft.
- **Probes:** click to drop extra seed points for the lines. The HUD reads out u, v, |u| and ΔT under the cursor.
- **Presets:** Still room, Clean candle, Snuffed, Hand wave, Steady breeze, Gusty draught.

**Physics:** incompressible Navier–Stokes with Boussinesq buoyancy (g·ΔT/T₀), heat advection and diffusion, and passive smoke. Stable fluids with MacCormack advection, a multigrid pressure solve, explicit viscosity (ν = 1.5×10⁻⁵ m²/s), and thermal diffusion (α = 2.2×10⁻⁵ m²/s). A check against Morton–Taylor–Turner plume theory is in the page: the candle plume runs 0.6–1.0 m/s, within ~25% of the law, and still-room air moves at 2–8 cm/s.

**Flagged:** source strengths (★ estimates), 2D slice rather than 3D (sources act as line sources, and the hand acts as a bar), numerical diffusion well above air's viscosity, and Boussinesq applied near the flame. All equations, constants, estimates, and known departures from reality are listed in the in-page **Physics & constants** panel.

Self-contained single HTML file with no network or libraries. Needs WebGL2 with float render targets (any recent desktop or phone browser).

---

Part of **Art Insights**, a series of interactive pieces by Hanji Xu. Open `index.html` in a current browser; it is a single self-contained file with no network access or libraries. See also [01 Stubble Field](https://github.com/Hanji-Xu/stubble-vector-field).
