# Florida Building Attributes GPT

**Created: December 4, 2025**

Florida Building Attributes GPT is designed to identify basic building attributes from aerial and street-level images, with a focus on buildings in Florida.

## How It Works

Provide:

1. **Year Built**
2. **Aerial Image** — Google Earth, satellite, or drone image
3. **Street-Level Image** — Google Street View or ground photograph
4. **Damaged Building Image** — optional, if available

One to three images of the same building can be provided.

The GPT visually analyzes the building and returns the estimated attributes in a horizontal table that can be copied into Excel.

## Building Attributes

### Roof Shape

Options:

`flat`, `hip`, `gable`, `monopitch`, `sawtooth`, `curved`, `complex_regular`, `complex_irregular`, etc.

### Roof Cover

Examples:

`Built-up roof`, `Single-ply membrane`, `Asphalt shingles`, `Metal roofing`, `Tile roofing`, etc.

### Roof Material

Options:

`masonry`, `earth`, `concrete`, `metal`, `wood`, `fabric`, `slate`, `stone`, `clay`, etc.

### Shape of Building

Options:

`square`, `rectangular`, `l_shape`, `curved`, `triangular`, `polygonal`, `e_shape`, `h_shape`, `s_shape`, `t_shape`, `u_c_shape`, `x-shape`, `y-shape`, etc.

### Number of Stories

The number of visible floors is estimated from the street-level image.

### Window Area

Options:

- `Low (<25%)`
- `Medium (25–40%)`
- `High (>40%)`

### Lateral Load Resisting System (LLRS)

Options:

`moment_frame`, `infilled_frame`, `braced_frame`, `post_beam`, `wall`, `dual_framewall`, `flat_slab`, `waffle_slab`, `infill_flatslab`, `infill_waffleslab`, `hybrid`, etc.

### Material of LLRS

Options:

`concrete_reinforced`, `concrete`, `concrete_steel`, `metal`, `masonary_reinforced`, `masonry`, `masonry_confined`, `earth`, `earth_reinforced`, `wood`, etc.

### Exterior Walls

Options:

`concrete`, `glass`, `earth`, `masonry`, `metal`, `vegetation`, `wood`, `stucco`, `plastic`, `vinyl`, `cement`, etc.

## Output

The GPT returns one horizontal table:

| Roof Shape | Roof Cover | Roof Material | Shape of Building | Number of Stories | Window Area | LLRS | Material of LLRS | Exterior Walls |
|---|---|---|---|---|---|---|---|---|
| hip | Type: Asphalt shingles | wood | rectangular | 1 | Low (<25%) | wall | masonry | stucco |

If an attribute cannot be determined confidently, the GPT adds **`(Unsure)`**.

When the LLRS or its material cannot be clearly identified from the images, the GPT uses the **year built and common Florida construction practices** to estimate the most likely option.
