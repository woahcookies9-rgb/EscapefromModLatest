# Vintage Computer Keyboard

A beige 101-key computer keyboard in the style of early 1990s office hardware,
modelled and UV-mapped by hand. Every keycap is a separate, named mesh, so keys can
be pressed, hidden or recoloured one at a time.

## 1. Contents

| Folder | What is in it |
|---|---|
| `Models/` | `Keyboard_Vintage.fbx` - 103 meshes (housing, cable, 101 keycaps) |
| `Materials/` | 7 materials on the Standard shader |
| `Textures/` | 4 PNG textures (2 base colour, 2 metallic/smoothness) |
| `Prefabs/` | `Keyboard_Vintage.prefab` - the assembled keyboard |
| `Demo/` | A scene showing the prefab lit and framed |

## 2. Quick start

Drag `Prefabs/Keyboard_Vintage` into your scene. The model is built at real-world
scale (1 unit = 1 metre) and its pivot sits at the centre of the housing footprint
with the underside at y = 0, so it drops onto a desk surface without any offset.
The row facing the typist points along +Z.

## 3. Using individual keys

Keycaps are named after the key they carry, not indexed:

- letters and digits: `Key_A`, `Key_7`
- named keys: `Key_Esc`, `Key_Space`, `Key_Enter`, `Key_Backspace`
- duplicated keys carry an L/R prefix: `Key_LShift`, `Key_RCtrl`, `Key_LAlt`
- numpad keys carry a `Num` prefix: `Key_Num7`, `Key_NumEnter`, `Key_NumSlash`

They live under the `Keycaps` child of the prefab root. To animate a keypress,
move the keycap down by roughly 3 mm along its local Y axis.

## 4. Render pipelines

The materials use the Standard shader and work in the Built-in Render Pipeline
out of the box.

For URP or HDRP, open `Window > Rendering > Render Pipeline Converter`, choose the
`Built-in to URP` (or HDRP) conversion, tick `Material Upgrade` and run it. The
meshes, UVs and textures need no changes.

## 5. Technical notes

- 25,422 triangles / 20,796 vertices in total. Each keycap is 156 triangles.
- One UV channel. Keycap legends come from a 16 x 8 atlas, one 256 x 256 cell per key.
- Lightmap UVs are not included in the FBX. If you bake lighting, tick
  `Generate Lightmap UVs` in the model import settings.
- Keep `Bake Axis Conversion` disabled in the model import settings. The axis
  conversion is already baked into the vertices.
- No rigging, no animations, no colliders and no LODs are included.

## 6. Support

Questions, bug reports and requests for extra layouts are welcome at:
dawidzielinski.programmer@gmail.com
