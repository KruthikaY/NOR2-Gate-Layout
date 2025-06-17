# 🔧 Full-Custom Mask Layout – 2-Input NOR Gate (ICD CMOS 0.3µm)

This repository documents the full mask-level design of a 2-input NOR gate using the ICD CMOS 0.3 µm (version G) process. It includes stick diagrams, layout design in L-Edit, process constraints, and verification.

---

## 📁 Repository Structure

- `stick_schematic/` – Stick-level logic and schematic visuals  
  ◦ `Stick diagram.png` – NOR2 stick routing diagram  
  ◦ `Stick diagrams` – Logic circuit diagram image  

- `Design rules/` – Technology rules and constraints  
  ◦ `Design rules.png` – CMOS 0.3 µm layout rule sheet  
  ◦ `Rules and constraints` – Textual constraints (ports, PR origin, spacing)  
  ◦ `constraints_dimensions.png` – Rule dimensions with labels  

- `layout_output/` – L-Edit layout and output reports  
  ◦ `NOR Gate (L-edit).png` – Final L-Edit layout screenshot  
  ◦ `Output` – Output or verification text  
  ◦ `ledit.pdf` – Complete drawn L-Edit layout (PDF export)  

- `Gate constraints.png` – Dimensions for PMOS/NMOS/L and W sizing  
- `README.md` – Full project documentation


---

## 🧠 Stick Diagram and Schematic

The NOR2 gate is realized using the standard CMOS topology:  
- **Pull-up network**: 2 PMOS transistors in series  
- **Pull-down network**: 2 NMOS transistors in parallel  

The stick diagram represents routing using color-coded layers (Poly, Metal1, Contacts), and includes global ports: `A`, `B`, `Y`, `Vdd!`, `GND!`.

---

## 📐 Design Rules (CMOS 0.3 µm)

The layout strictly follows the [ICD CMOS 0.3µm Version G] rules. Key constraints include:

| Layer         | Rule Type                                | Value (µm) |
|---------------|-------------------------------------------|------------|
| Poly          | Min width / spacing                      | 0.3 / 0.5  |
| Metal1        | Min width / spacing                      | 0.5 / 0.5  |
| Contacts      | Size / spacing to Poly / Active          | 0.3 / 0.3  |
| N-Well        | Min width / spacing                      | 2.0 / 1.0  |
| Active Area   | Min width / spacing / S-D length         | 0.5 / 0.6 / 0.5 |

> Full reference in: `Design rules.png` and `constraints_dimensions.png`

---

## ✨ Technology and Constraints

- **Process**: ICD CMOS 0.3µm (version G)
- **Tools Used**: [L-Edit 2021.2]
- **Transistor Specs**:
  - PMOS: L = 0.3µm, W = 2.5µm
  - NMOS: L = 0.3µm, W = 1.0µm
- **Metal1 Power Rail Width**: 0.8 µm

**Naming and Port Rules**:
- Cell name: `NOR2` (case-sensitive)
- Port names: `A`, `B`, `Y`, `Vdd!`, `GND!`
- PR Boundary origin: (0,0)
- Input/output ports must be drawn on **polysilicon** layer  
- Vdd! and GND! ports drawn on **metal1**

📌 *Ensure zero-width ports align with the conductor edge on PR boundary.*

---

## 🖼️ Layout and Output

- Final layout verified in `L-Edit` and exported as `NOR Gate (L-edit).png`
- `ledit.pdf` contains the full drawn layout using standard CMOS layers

---

## ✅ Outcome

- Fully DRC-compliant NOR2 layout
- Adheres to industry mask design rules
- Easy to reuse as a custom standard cell

---

## 📎 References

- ICD CMOS 0.3 µm G-Process DRC
- Tanner EDA: L-Edit v2021.2
