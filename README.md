# Physics Formula Cheat Sheet

An interactive physics formula reference sheet built for Czech high school / medical entrance exam preparation. All formulas are clickable and open a detailed popup explaining each variable.

---

## How It Works

The entire site is a single `index.html` file. It contains three parts all in one file:

- **HTML** — the structure and content (all the formula cards)
- **CSS** — the styling (dark theme, colors, layout, modal design)
- **JavaScript** — the click-to-expand popup functionality

No frameworks, no dependencies, no internet required to run locally.

---

## How to Add a New Formula

Find the relevant topic card in the HTML and copy an existing `formula-block` div. It looks like this:

```html
<div class="formula-block" onclick="openModal('Topic Name', 'FORMULA HERE', [
  ['variable','description of variable and its units'],
  ['variable2','description of variable2 and its units']
], 'Optional tip or note shown at the bottom of the popup')">
  <div class="formula">FORMULA HERE</div>
  <div class="vars">short description shown on the card</div>
</div>
```

### The `openModal()` function takes 4 arguments:
| Argument | What it is | Example |
|---|---|---|
| 1st | Topic name shown at top of popup | `'Kinematics'` |
| 2nd | The formula itself | `'v = s / t'` |
| 3rd | Array of [variable, description] pairs | `[['v','velocity (m/s)'], ['s','distance (m)']]` |
| 4th | Optional tip note (or `null` for none) | `'Only works at constant speed'` |

---

## How to Add a New Topic Card

Copy this template and paste it inside the `<div class="grid">`:

```html
<div class="card">
  <div class="card-title">XX · Czech Name — English Name</div>

  <div class="formula-block" onclick="openModal('Topic', 'F = ma', [
    ['F','force (N)'],
    ['m','mass (kg)'],
    ['a','acceleration (m/s²)']
  ], 'Optional tip here')">
    <div class="formula">F = ma</div>
    <div class="vars">short summary of what formula does</div>
  </div>

</div>
```

Cards automatically get color-coded top borders cycling through purple → teal → red → yellow.

---

## How to Change the Colors

At the top of the file inside `<style>`, find the `:root` block:

```css
:root {
  --bg: #0a0a0f;          /* page background */
  --surface: #12121a;     /* formula block background */
  --card: #1a1a26;        /* card background */
  --border: #2a2a3e;      /* border color */
  --accent1: #7c6af7;     /* purple — card stripe & hover */
  --accent2: #4ecdc4;     /* teal */
  --accent3: #ff6b6b;     /* red */
  --accent4: #ffd93d;     /* yellow */
  --text: #e8e8f0;        /* main text */
  --muted: #8888a8;       /* secondary/dim text */
  --formula: #c8f0e8;     /* formula text color */
}
```

Change any hex value to update that color across the whole site.

---

## Topics Covered

| # | Czech | English |
|---|---|---|
| 02 | Kinematika | Kinematics |
| 03 | Dynamika | Dynamics |
| 04 | Gravitační zákon | Gravitation |
| 05 | Rovnoměrný pohyb po kružnici | Circular Motion |
| 06 | Práce, energie, výkon | Work, Energy, Power |
| 07 | Hydrostatika | Hydrostatics |
| 08 | Hydrodynamika | Hydrodynamics |
| 10 | Hookův zákon | Hooke's Law |
| 11 | Kmitání, vlnění, akustika | Oscillations, Waves, Acoustics |
| 12 | Termodynamika | Thermodynamics |
| 13 | Elektřina a elektrický proud | Electricity & Current |
| 14 | Magnetismus a střídavý proud | Magnetism & AC |
| 15 | Optika | Optics |
| 16 | Mikrosvět | Quantum & Atomic Physics |

---

## Hosted On

GitHub Pages — any push to the `main` branch automatically updates the live site.
