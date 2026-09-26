# 🦸 Marvel Superheroes RPG FEAT Roller

A single-page, dependency-free web app for resolving **FEAT** (Function of
Exceptional Ability or Talent) checks in the 1980s **Marvel Super Heroes
Role Playing Game (MSRPG)**. Pick a FEAT, pick a Rank, optionally spend some
Karma, and roll — the app looks up the Universal Table for you and tells
you the color result, the effect, and what that effect means.

The whole app is a single `index.html` file with no build step and no
external dependencies, so it runs equally well from GitHub Pages, any
static file host, or just opened directly from disk.

## Using it

1. **Choose a FEAT** from the dropdown. FEATs are grouped into:
   - **Pre-Action Rolls** — Multiple Attacks - 2 and Multiple Attacks - 3.
     These are Fighting FEATs against a Remarkable or Amazing Intensity.
     Once you pick a Rank, the app shows which color you need (Green,
     Yellow, or Red), or tells you the FEAT is an automatic success or
     impossible at that Rank. The result is a simple success/failure.
   - **Attacks & Actions** — Blunt Attack, Edged Attack, Shooting, Throwing
     Edged, Throwing Blunt, Energy, Force, Grappling, Grabbing, Escaping,
     Charging, Dodging, Evading, Blocking, Catching
   - **Resolution Checks** — Stun, Slam, and Kill FEATs (the Endurance-based
     checks made after certain attack results)
2. The **Ability** the selected FEAT is based on (Fighting, Agility,
   Strength, or Endurance) is shown automatically — it's read-only and
   always follows the FEAT you picked.
3. **Choose a Rank** (Shift 0 through Beyond) from the Universal Table.
4. Optionally enter a **Karma** value (0–99) to add to the roll. It
   defaults to 0. Out-of-range or non-numeric entries are automatically
   clamped/reset when you leave the field.
5. Click **Roll FEAT**. The app:
   - Rolls a random number from 1–100
   - Adds your Karma
   - Clamps the total back to the 1–100 range
   - Looks up the result on the Universal Table for the selected Rank to
     get a color (White, Green, Yellow, or Red)
   - Looks up that color's effect for the selected FEAT (e.g. a Yellow
     result on a Blunt Attack is a "Slam")
   - Shows a plain-language description of that effect
6. If a result's effect is **Slam**, **Stun**, or **Kill**, a banner
   appears prompting you to roll the matching resolution FEAT. Clicking it
   reveals a nested roller with its own independent Rank and Karma inputs
   (since that check is typically made by a different character/target
   than the one who just rolled). Resolution FEATs can also always be
   rolled directly by selecting them from the main dropdown.
7. Every roll (primary and resolution) is appended to a **Roll History**
   list at the bottom of the page, most recent first. History is
   in-memory only and resets on page reload — nothing is saved between
   sessions.

## License

See [LICENSE](LICENSE).
