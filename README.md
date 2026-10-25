# SpanLab — Structural Beam Studio

![HTML5](https://img.shields.io/badge/HTML5-Single_File-e34f26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-Responsive-1572b6?logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-Interactive-f7df1e?logo=javascript&logoColor=111)
![License](https://img.shields.io/badge/License-Educational-b6f45d)

**SpanLab** is an interactive structural-engineering learning tool for exploring how a simply supported rectangular beam responds to a single point load.

Change the span, load position, section dimensions, or material and see the reactions, bending moment, estimated deflection, and utilization update instantly.

> Designed for engineering students, educators, and early-stage structural concept exploration.

## Repository Name

```text
spanlab-structural-engineering
```

## Highlights

| Feature | Description |
|---|---|
| Interactive beam model | Move the point load and observe the diagram update |
| Support reactions | Calculates the left and right reactions automatically |
| Bending response | Calculates the maximum bending moment and stress |
| Deflection estimate | Uses elastic beam theory to estimate displacement |
| Material library | Includes steel, concrete, timber, and aluminium |
| Section controls | Adjustable rectangular-section width and depth |
| Utilization meter | Compares bending stress with a simplified material limit |
| Responsive interface | Works on desktop, tablet, and mobile screens |
| Local operation | Performs all calculations inside the browser |
| Zero dependencies | Uses one self-contained HTML file |

## Preview

The application contains:

- A structural input panel
- An animated beam-and-load diagram
- Live reaction, moment, and deflection results
- A color-coded utilization meter
- A clear `PASS` or `REVIEW` status
- Responsive desktop and mobile layouts

## Technologies

- **HTML5** for semantic structure
- **CSS3** for the responsive engineering dashboard
- **Vanilla JavaScript** for calculations and interactions
- **No frameworks, packages, APIs, or build tools**

## Project Structure

```text
spanlab-structural-engineering/
├── index.html
└── README.md
```

## Quick Start

### Option 1: Open directly

1. Download or clone the repository.
2. Open the project directory.
3. Double-click `index.html`.

### Option 2: Use a local server

Run the following command from the project directory:

```bash
python3 -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

## How to Use SpanLab

1. Set the **beam span** in metres.
2. Choose the **point load** in kilonewtons.
3. Set the **load position** along the span.
4. Enter the rectangular section's **width** and **depth**.
5. Select the beam **material**.
6. Review the calculated structural response.
7. Use **Reset model** to restore the original values.

The results update immediately whenever an input changes.

## Available Materials

| Material | Elastic modulus used | Simplified stress limit |
|---|---:|---:|
| Structural steel | 200 GPa | 250 MPa |
| Concrete | 30 GPa | 25 MPa |
| Timber | 11 GPa | 12 MPa |
| Aluminium | 70 GPa | 160 MPa |

These are simplified demonstration values. Real design values depend on material grade, orientation, condition, safety factors, limit state, and the applicable design standard.

## Engineering Model

SpanLab models a simply supported beam carrying one downward point load.

### Support Reactions

```text
RA = P(L − a) / L
RB = Pa / L
```

Where:

- `P` = applied point load
- `L` = total beam span
- `a` = distance from the left support to the load
- `RA` = left support reaction
- `RB` = right support reaction

### Maximum Bending Moment

The maximum moment occurs beneath the point load:

```text
Mmax = RA × a
```

### Rectangular-Section Properties

```text
I = bh³ / 12
Z = bh² / 6
```

Where:

- `b` = section width
- `h` = section depth
- `I` = second moment of area
- `Z` = elastic section modulus

### Bending Stress

```text
σ = Mmax / Z
```

### Deflection at the Point Load

For a point load located at distances `a` and `b₁ = L − a` from the supports:

```text
δ = Pa²b₁² / (3EIL)
```

Where:

- `δ` = deflection at the point load
- `E` = elastic modulus
- `I` = second moment of area
- `L` = total beam span

## Units

| Input or result | Unit |
|---|---|
| Beam span | m |
| Load position | Percentage of span |
| Point load | kN |
| Support reactions | kN |
| Section width and depth | mm |
| Bending moment | kN·m |
| Elastic modulus | MPa |
| Bending stress | MPa |
| Deflection | mm |

The JavaScript converts values internally to maintain consistent units during calculations.

## Utilization Status

SpanLab compares the calculated bending stress with the simplified stress limit assigned to the selected material.

```text
Utilization = Calculated stress / Material limit × 100
```

The application displays:

- **PASS** when utilization is at or below 100%
- **REVIEW** when utilization exceeds 100%

The utilization meter changes color as the result approaches or exceeds the selected limit.

## Customization

The complete application is contained in `index.html`, making it easy to customize.

You can:

- Edit the CSS variables inside `:root` to change the theme
- Add new materials to the material selection menu
- Change slider ranges for different project scales
- Add new result cards
- Introduce shear-force calculations
- Add new cross-section types
- Add metric and imperial units
- Export calculations as a report

## Current Limitations

- Supports only one point load
- Uses only a simply supported beam
- Uses only a rectangular cross-section
- Assumes linear elastic behavior
- Assumes small displacement
- Does not check shear capacity
- Does not check lateral or local buckling
- Does not check vibration or fatigue
- Does not include connection design
- Does not apply load combinations or code-specific safety factors
- Does not model reinforced-concrete cracking or reinforcement
- Does not replace professional structural-analysis software

## Roadmap

- [ ] Uniformly distributed loads
- [ ] Multiple point loads
- [ ] Shear-force diagram
- [ ] Bending-moment diagram
- [ ] Deflected-shape animation
- [ ] I-section profile
- [ ] Circular section
- [ ] Hollow rectangular section
- [ ] Metric and imperial unit switching
- [ ] Calculation-report export
- [ ] Saved design scenarios
- [ ] Dark and light themes
- [ ] Code-specific design modules

## Contributing

Contributions are welcome.

1. Fork the repository.
2. Create a feature branch.

```bash
git checkout -b feature/new-feature
```

3. Make and test your changes.
4. Commit the changes.

```bash
git commit -m "Add new structural feature"
```

5. Push your branch.

```bash
git push origin feature/new-feature
```

6. Open a pull request describing the improvement.

Please keep the project accessible, dependency-free, and suitable for engineering education.

## Important Engineering Disclaimer

SpanLab is provided only for education, visualization, and preliminary concept exploration.

It must not be used as the sole basis for construction, fabrication, procurement, or safety-critical decisions.

A qualified engineer must verify every real design using:

- Accurate material properties
- Verified permanent and variable loads
- Governing load combinations
- Strength and stability checks
- Serviceability requirements
- Connection design
- Structural detailing requirements
- Applicable national or international standards

## License

This project is available for personal and educational use. You may modify and expand it for learning or portfolio purposes.

## Author Note

Built as a compact engineering project demonstrating structural mechanics, numerical calculation, responsive interface design, and browser-based visualization without external dependencies.# SpanLab — Structural Beam Studio

SpanLab is a responsive structural engineering web application for exploring the behavior of a simply supported beam under a single point load. Users can change the span, load, load position, cross-section dimensions, and material to see updated structural results instantly.

## Repository Name

`spanlab-structural-engineering`

## Features

- Interactive simply supported beam model
- Adjustable beam span and point load
- Adjustable load position
- Custom rectangular section width and depth
- Structural steel, concrete, timber, and aluminium options
- Automatic support-reaction calculations
- Maximum bending-moment calculation
- Approximate beam-deflection calculation
- Bending-stress utilization indicator
- Pass or review safety status
- Animated load-position visualization
- Responsive mobile and desktop design
- No installation or external libraries required

## Technologies Used

- HTML5
- CSS3
- Vanilla JavaScript

## Project Structure

```text
spanlab-structural-engineering/
├── index.html
└── README.md
