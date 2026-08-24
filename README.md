# 🏢 Florida Building Attributes GPT

**Florida Building Attributes** is a specialized computer-vision GPT designed to estimate structural and architectural characteristics of buildings from aerial and street-level imagery.

It is primarily designed for **buildings in Florida** and uses visual evidence, construction characteristics, and year-built information to produce a standardized set of building attributes.

The goal is to make building-image assessment **faster, consistent, and easy to transfer into Excel, GIS, or building-inventory datasets**.

## 🔍 What It Does

Provide the GPT with the **year built** and one or more images of the same building, such as:

- 🛰️ **Aerial imagery** — Google Earth, satellite, or drone imagery
- 🏠 **Street-level imagery** — Google Street View or ground photographs
- 🏚️ **Post-damage imagery** — photographs showing a damaged building

The GPT visually evaluates the available evidence and estimates a predefined set of building attributes.

## 🧱 Attributes Identified

The GPT estimates:

| Attribute | Example |
|---|---|
| Roof Shape | hip |
| Roof Cover | Type: Asphalt shingles |
| Roof Material | wood |
| Shape of Building | rectangular |
| Number of Stories | 1 |
| Window Area | Low (<25%) |
| Lateral Load Resisting System (LLRS) | wall |
| Material of LLRS | masonry |
| Exterior Walls | stucco |

### Roof Shape

Examples include:

`flat`, `hip`, `gable`, `monopitch`, `sawtooth`, `curved`, `complex_regular`, and `complex_irregular`.

Aerial imagery is particularly useful for determining roof geometry and building footprint.

### Roof Cover

The GPT estimates the visible roof-covering system, such as:

- Asphalt shingles
- Built-up roof
- Single-ply membrane
- Metal roofing
- Tile roofing

### Roof Material

The likely structural roof material is estimated separately from the roof covering.

Examples include:

`masonry`, `concrete`, `metal`, `wood`, `slate`, `stone`, and `clay`.

### Building Shape

The building footprint is classified into forms such as:

`square`, `rectangular`, `l_shape`, `curved`, `triangular`, `polygonal`, `e_shape`, `h_shape`, `s_shape`, `t_shape`, `u_c_shape`, `x-shape`, and `y-shape`.

### Number of Stories

Visible floors are counted primarily from the street-level imagery.

### Window Area

The visible façade is classified using three standardized categories:

- **Low:** <25% window area
- **Medium:** 25–40% window area
- **High:** >40% window area

### Lateral Load Resisting System

The GPT estimates the most likely **Lateral Load Resisting System (LLRS)**.

Possible classifications include:

`moment_frame`, `infilled_frame`, `braced_frame`, `post_beam`, `wall`, `dual_framewall`, `flat_slab`, `waffle_slab`, `infill_flatslab`, `infill_waffleslab`, and `hybrid`.

Because the structural system is often concealed by exterior finishes, this attribute cannot always be determined directly from photographs.

When visual evidence is insufficient, the GPT uses the **year built, visible construction characteristics, building type, and common Florida construction practices** to determine the most likely classification.

### LLRS Material

Possible structural materials include:

`concrete_reinforced`, `concrete`, `concrete_steel`, `metal`, `masonary_reinforced`, `masonry`, `masonry_confined`, `earth`, `earth_reinforced`, and `wood`.

### Exterior Walls

Visible exterior wall materials may include:

`concrete`, `glass`, `earth`, `masonry`, `metal`, `vegetation`, `wood`, `stucco`, `plastic`, `vinyl`, and `cement`.

## 📊 Standardized Output

Results are deliberately returned as a **single horizontal table**.

This makes the output easy to copy directly into:

- Microsoft Excel
- Google Sheets
- GIS attribute tables
- Building inventory databases
- Exposure and vulnerability datasets
- Post-disaster building assessments

Example:

| Roof Shape | Roof Cover | Roof Material | Shape of Building | Number of Stories | Window Area | Lateral Load Resisting System (LLRS) | Material of LLRS | Exterior Walls |
|---|---|---|---|---:|---|---|---|---|
| hip | Type: Asphalt shingles | wood | rectangular | 1 | Low (<25%) | wall | masonry | stucco |

If an attribute cannot be determined confidently, the GPT marks the result with **`(Unsure)`** rather than presenting the estimate as certain.

## 🌴 Why Florida?

Florida has distinctive construction practices influenced by:

- Hurricane and wind-load requirements
- Coastal exposure
- Flood risk
- Changes in building codes over time
- Extensive use of concrete masonry construction
- Wood-frame residential construction
- Stucco exterior finishes
- Hip and gable roof systems
- Shingle, tile, membrane, and metal roofing

The GPT therefore uses **Florida construction practices as its default regional context** when visual evidence alone is insufficient.

This is particularly important when estimating structural attributes that cannot be directly observed from exterior photographs.

## 💡 Potential Applications

Florida Building Attributes can support workflows involving:

- 🌀 Hurricane vulnerability and risk assessment
- 🏚️ Post-disaster building surveys
- 🗺️ GIS building inventories
- 🏙️ Urban-scale building characterization
- 🏗️ Structural typology classification
- 📊 Exposure modeling
- 🛡️ Insurance and catastrophe-risk research
- 🔬 Academic research
- 🤖 AI-assisted building image analysis

## ⚠️ Important Limitations

The GPT performs **visual estimation**, not a structural inspection.

Some attributes—particularly structural systems, concealed materials, roof structural materials, and LLRS classifications—cannot be conclusively identified from exterior imagery alone.

Results should therefore be treated as **AI-assisted classifications or estimates**.

They should not replace:

- Engineering inspections
- Architectural or structural drawings
- Building permits
- Property records
- Code-compliance assessments
- Professional structural evaluations

Image quality, viewing angle, vegetation, neighboring structures, façade modifications, roof visibility, and post-construction renovations can all affect classification accuracy.

## 🚀 Basic Workflow

**1. Provide the year built**

Example:

`Year Built: 1985`

**2. Upload available building imagery**

Ideally provide both an aerial and street-level image of the same structure.

**3. Receive standardized attributes**

The GPT analyzes the images and returns one horizontal table containing the estimated building characteristics.

**4. Transfer the results**

Copy the resulting row directly into Excel, a spreadsheet, GIS workflow, or another building database.

## 🎯 Project Goal

Florida Building Attributes is intended to explore how multimodal AI can assist with **rapid, standardized building characterization from imagery**.

Rather than producing lengthy descriptions of buildings, the GPT focuses on a concise set of attributes useful for structured building inventories and vulnerability-analysis workflows.

---

### Disclaimer

**Florida Building Attributes is an experimental AI-assisted building classification tool. Outputs may contain errors or uncertain classifications. Structural characteristics should be independently verified when used for engineering, safety, insurance, regulatory, or other consequential decisions.**
