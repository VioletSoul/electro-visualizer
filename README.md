# Electro Visualizer Ultimate

<!-- Core -->
![Project](https://img.shields.io/badge/project-Electro%20Visualizer%20Ultimate-01696f)
![Status](https://img.shields.io/badge/status-final-16a34a)
![Platform](https://img.shields.io/badge/platform-browser-1f6feb)
![Form](https://img.shields.io/badge/form-single--file_HTML-0a7ea4)

<!-- Tech -->
![Stack](https://img.shields.io/badge/stack-HTML%20%7C%20CSS%20%7C%20JS-7c3aed)
![Charts](https://img.shields.io/badge/charts-Chart.js-ff6384)

<!-- Domain / features -->
![Domain](https://img.shields.io/badge/domain-electrical%20engineering-0f766e)
![Groups](https://img.shields.io/badge/groups-Basic%20%7C%20Advanced%20%7C%20Pro-2563eb)
![Sweeps](https://img.shields.io/badge/sweeps-tables%20%26%20plots-059669)
![Export](https://img.shields.io/badge/export-CSV-16a34a)
![Theme](https://img.shields.io/badge/theme-light%20%2F%20dark-475569)

<!-- Meta -->
![Docs](https://img.shields.io/badge/docs-RU-6b7280)
![Offline](https://img.shields.io/badge/offline-supported-334155)

**Electro Visualizer Ultimate** is the final unified version of an engineering HTML tool that combines basic, advanced, and pro modes in a single standalone file. The app runs locally in the browser, requires no build step or backend, and combines quick calculations, sweep analysis, charts, tables, and CSV export.

The Ultimate release keeps all computational functionality in one interface: navigation by mode groups on the left, a parameters and results panel in the center, a chart and sweep table below, and at the top a strip with the active mode, key result, secondary metric, and the sweep point count.

This document describes the purpose of the app, its architecture, supported modes, mathematical model, UI structure, data formats, usage scenarios, and the limitations of the final Ultimate build.

---

## Table of contents

- [Overview](#overview)
- [What changed in Ultimate](#what-changed-in-ultimate)
- [Key capabilities](#key-capabilities)
- [Who this is for](#who-this-is-for)
- [Architecture](#architecture)
- [Interface structure](#interface-structure)
- [Mode groups](#mode-groups)
- [Supported engineering modes](#supported-engineering-modes)
- [Mathematical model](#mathematical-model)
- [Result formats](#result-formats)
- [Sweep modes and tabular analysis](#sweep-modes-and-tabular-analysis)
- [Charts and visualization](#charts-and-visualization)
- [Data export](#data-export)
- [Typical usage scenarios](#typical-usage-scenarios)
- [Practical value](#practical-value)
- [How to run and use](#how-to-run-and-use)
- [Repository structure](#repository-structure)
- [Limitations](#limitations)
- [FAQ](#faq)
- [Feature checklist](#feature-checklist)
- [License](#license)

---

## Overview

**Electro Visualizer Ultimate** is a standalone HTML application for computing, exploring, and visualizing electrical quantities that frequently appear in electric circuits, electronics, and circuit theory courses.

Unlike a simple calculator, the app does not stop at a single number. It tries to show an electrical quantity in several forms at once:

- as a numeric result;
- as a derived related quantity;
- as a curve on a chart;
- as a set of points in a sweep mode;
- as a complex number;
- as a phasor-style interpretation;
- as a tabular dataset ready for export.

In essence it is not just one calculator but a compact engineering mini-bench packed into a single file.

---

## What changed in Ultimate

Ultimate is not just a rename of an older version. It is a final unified build where all major modes are merged into a single working environment.

Key changes:

- Instead of disjoint modes there is a single navigation split into **Basic**, **Advanced**, and **Pro** groups.
- All calculations share the same interface structure: parameters, results, chart, sweep table.
- Advanced modes have been added and unified, including tolerance, sensitivity, Monte Carlo, harmonics, and three‑phase.
- The single-file HTML format is preserved.
- The final layout was reworked so that sidebar, summary, results, and the chart area form one coherent UI structure.

---

## Key capabilities

The app brings together the following functional groups:

- DC calculations: Ohm’s law, power, energy, conductor resistance, voltage divider.
- AC calculations: reactive impedances, total impedance, phase angle, active/reactive/apparent power.
- Complex analysis: rectangular and polar form, magnitude, angle, real and imaginary parts.
- Phasors: phase shift, sinusoidal signals, time-domain interpretation of voltage and current.
- RC/RL filters: time constant, cutoff frequency, sweep and chart-based exploration.
- RLC circuits: resonance, impedance vs frequency, Q‑factor.
- Sweep modes: building tabular datasets over a chosen parameter range.
- CSV export: downloading the current sweep dataset for external tools.
- Additional engineering analysis: tolerance, sensitivity, Monte Carlo, THD, three‑phase.

---

## Who this is for

The app is useful for several groups of users.

### 1. Students

Helps solve circuit problems, verify hand calculations, see relationships between quantities, and better understand AC analysis.

### 2. Instructors

Convenient as a demo tool in class, since formulas can be directly linked to charts and sweep tables.

### 3. Hobbyists and practitioners

Good for quick engineering estimates, impedance and filter checks, phase shifts, resonance effects, and sensitivity to parameters.

### 4. Engineers

Can serve as a compact local tool for preliminary calculations and visual analysis before heavier simulations or full design work.

---

## Architecture

Ultimate is designed as an engineering workspace rather than a set of isolated forms.

The architecture follows several principles:

### 1. Single standalone HTML file

The app opens locally in the browser and does not need a server, dependency installation, or backend.

### 2. Multiple representations of the same quantity

For example, impedance can be viewed:

- as a complex number;
- as magnitude;
- as phase angle;
- as a sweep of values;
- as a curve on a chart.

### 3. Calculation plus exploration

The app combines:

- a point calculation mode, when a specific value is needed;
- a parametric exploration mode, when the shape of the dependency matters.

### 4. Unified UI template

Whatever the active mode, the user works in the same visual scheme:

- choose a mode;
- enter parameters;
- inspect result cards;
- view the chart;
- analyze the table;
- export CSV if needed.

### 5. Practical portability

Opens in nearly any modern browser as a ready-made static engineering tool.

---

## Interface structure

The final version is organized as a single workspace.

### 1. Sidebar

The left panel contains:

- a branding block;
- theme toggle;
- active mode reset;
- navigation by sections.

The sidebar splits sections into **Basic**, **Advanced**, and **Pro**.

### 2. Top summary strip

The top of the main area shows:

- the active section name;
- a short mode description;
- a key formula or expression;
- four summary cards: mode, key result, secondary metric, and sweep point count.

### 3. Parameters panel

Includes:

- submode selector;
- input fields for source quantities;
- a calculate button;
- CSV export.

### 4. Results panel

Shows:

- main result;
- auxiliary computed values;
- derived electrical characteristics;
- complex-view or textual interpretation of the result.

### 5. Chart area

Used for:

- time-domain plots;
- frequency response plots;
- sweep curves;
- magnitude and phase plots.

### 6. Table area

Displays sweep point sets and serves as a basis for CSV export.

---

## Mode groups

Ultimate uses three main navigation groups:

| Group | Purpose |
|---|---|
| **Basic** | Basic calculations, everyday electrical tasks, materials, and dividers. |
| **Advanced** | AC modes, filters, bridge and intermediate engineering modes. |
| **Pro** | Complex analysis, RLC, phasors, sweep, tolerance, sensitivity, Monte Carlo, harmonics, and three‑phase. |

This split makes the app suitable both for quick educational tasks and deeper engineering analysis.

---

## Supported engineering modes

Below are the main mode groups in the final Ultimate version.

### 1. Basic

Used for basic calculations and resistive circuits.

#### Includes

- Ohm’s law
- Power
- Energy
- Conductor resistance
- Voltage divider

#### Can compute

- Voltage, current, resistance
- Power dissipation
- Stored energy over time
- Resistance by length, material, and cross-section area
- Divider output voltage

### 2. Advanced

Used for AC analysis, filters, and mid-level engineering tasks.

#### Includes

- Reactive impedances
- AC power
- RC low‑pass
- RL high‑pass
- Time constants
- Bridge circuits

#### Can compute

- XL
- XC
- P, Q, S
- Cutoff frequencies
- Time constants
- Sweep charts and tables for filters and bridges

### 3. Pro

The most feature-rich engineering group in the final version.

#### Includes

- Complex impedance
- Complex power
- RLC analysis
- Phasors and waveforms
- Sweep modes
- Tolerance
- Sensitivity
- Monte Carlo
- Harmonics / THD
- Three‑phase

#### Can analyze

- complex form of electrical quantities;
- phase angle;
- real and imaginary parts;
- RLC behavior near resonance;
- sensitivity to parameter variations;
- parameter spread;
- harmonic content;
- basic three‑phase calculations.

---

## Mathematical model

Key formulas used in the app.

### Ohm’s law

- U = I * R
- I = U / R
- R = U / I

### Electric power

- P = U * I
- P = I² * R
- P = U² / R

### Energy

- E = P * t

### Conductor resistance

- R = rho * L / S

where:

- R — resistance
- rho — material resistivity
- L — conductor length
- S — cross-sectional area

### Voltage divider

- Uout = Uin * R2 / (R1 + R2)

### Inductive reactance

- XL = 2 * pi * f * L

### Capacitive reactance

- XC = 1 / (2 * pi * f * C)

### Complex impedance

General:

- Z = R + jX

For a series RLC circuit:

- Z = R + j (XL − XC)

### Magnitude of impedance

- |Z| = sqrt(R² + X²)

### Phase angle

- phi = arctan(X / R)

### Complex power

- S_complex = P + jQ
- S = U * I
- P = U * I * cos(phi)
- Q = U * I * sin(phi)

### Cutoff frequency

For RC:

- fc = 1 / (2 * pi * R * C)

For RL, equivalent formulas in terms of R and L are used.

### Time constant

For RC:

- tau = R * C

For RL:

- tau = L / R

### Resonant frequency

- f0 = 1 / (2 * pi * sqrt(L * C))

---

## Result formats

One of the main strengths of the app is multi-format representation of results.

### 1. Scalar form

Used for simple DC quantities and derived values.

Examples:

- R = 220 Ohm
- I = 0.05 A
- P = 0.55 W

### 2. Complex form

Used for AC and impedance models.

Example:

`Z = 10 + j15 Ohm`

### 3. Polar form

Used when magnitude and angle are important.

Example:

`Z = 18.03 angle 56.31 deg Ohm`

### 4. Tabular form

Used in sweep modes as a set of points.

| Parameter | Value 1 | Value 2 | ... |
|---|---:|---:|---:|
| Frequency | ... | ... | ... |
| Amplitude | ... | ... | ... |
| Phase | ... | ... | ... |

### 5. Graphical form

Used to visualize how a quantity changes over time, frequency, or another swept parameter.

---

## Sweep modes and tabular analysis

Sweep modes are one of the most important features. Instead of computing a single point, the user specifies a parameter range and the app builds a sequence of calculations.

### What can be swept

Depending on the mode:

- frequency;
- resistance;
- capacitance;
- inductance;
- time;
- phase angle;
- another control variable.

### Outputs

- a set of discrete points;
- a value table;
- a curve on a chart;
- an option to export to CSV.

### Why it matters

Sweep modes reveal:

- resonance regions;
- impedance trends;
- filter behavior;
- sensitivity of results to parameters;
- inflection points and critical zones.

---

## Charts and visualization

Charts are a primary tool for understanding electrical relationships.

### Visualization types

Depending on the mode:

- time-domain plots;
- frequency response;
- sweep curves;
- magnitude/phase plots;
- comparative engineering curves.

### What charts reveal

Charts show what individual numbers hide:

- growth or decay;
- resonance behavior;
- phase shift;
- sensitivity to parameter changes;
- how a quantity behaves over a range rather than at one point.

---

## Data export

The app can export the current sweep table to CSV.

### Why it is useful

CSV can be used for:

- importing into Excel;
- Google Sheets;
- building additional plots;
- analysis in Python / MATLAB / Octave;
- lab reports and documentation.

### Typical workflow

1. Select a mode.
2. Configure the sweep.
3. Generate the table.
4. Click export.
5. Get a CSV file with the current data.

---

## Typical usage scenarios

Some representative usage patterns.

### Scenario 1. Quick check of a problem

The user knows the circuit parameters and wants to quickly check a result.

Good for:

- Ohm’s law;
- power;
- dividers;
- RC/RL parameters.

### Scenario 2. Exploring filter behavior

The user changes frequency and observes the circuit response.

Good for:

- RC low‑pass;
- RL high‑pass;
- impedance vs frequency.

### Scenario 3. Complex impedance analysis

The user wants to see a quantity both as rectangular and polar form.

Good for:

- AC analysis;
- RLC circuits;
- phasors.

### Scenario 4. Preparing a report or lab work

The user builds a sweep table and exports data for further processing.

### Scenario 5. Spread and sensitivity analysis

The user wants to see how sensitive a result is to tolerance or parameter changes.

Good for:

- tolerance;
- sensitivity;
- Monte Carlo.

### Scenario 6. Teaching demonstration

An instructor or student explains how frequency affects reactance, resonance, phase, or response shape.

---

## Practical value

The app is useful not only as a teaching tool but also as a quick way to build engineering intuition. It is especially handy for:

- learning;
- hypothesis checking;
- selecting component values;
- explaining electrical effects;
- rapid engineering estimates without heavy CAD/CAE tools.

---

## How to run and use

### Local run

The app is a single HTML file.

To start:

1. Save the HTML file.
2. Open it in a modern browser.
3. Choose the desired mode group in the sidebar.
4. Select a specific submode.
5. Enter parameters.
6. Inspect results, charts, and tables.
7. Export CSV if needed.

### Where it fits well

The app is especially convenient for:

- offline local use;
- demos;
- quick on‑site calculations;
- storing in a repository as a portable tool.

---

## Repository structure

Repository layout (under construction):

```text
project-root/
├── electro-visualizer-ultimate.html
├── README.md
└── docs/
    └── screenshots/
        ├── main-ui.png
        ├── basic-modes.png
        ├── advanced-modes.png
        └── pro-modes.png
```
---

## Limitations
Despite the wide feature set, the app is not a full replacement for professional simulators.
### Current limitations
-	Not a SPICE simulator.
-	No numerical simulation of complex nonlinear circuits.
-	No full interactive schematic editor.
-	No multi-project scenario storage.
-	No CAS-level symbolic algebra engine.
-	No full nonlinear device simulation.

What this means in practice:
The app is ideal for typical dependencies, variation analysis, and visualization, but it is not meant to be a complete electronic design environment.

---

## FAQ

### What is this: a website, a calculator, or an engineering tool?

It is an engineering HTML visualizer with calculator functions, charting, sweep export, and a small research workbench.

### Is this the final version?

Yes. This README describes the final Ultimate build: a single HTML file with the full set of modes and the unified interface.

### Do I need a server to run it?

No. It runs locally as a regular HTML file.

### Is it suitable for learning?

Yes. It is particularly useful for education because it links formulas, numbers, phase, charts, and sweep tables.

### Does it replace SPICE?

No. It is not a full circuit simulator, but a compact visual and computational tool.

### Can results be used in external tools?

Yes. Sweep data can be exported to CSV.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.