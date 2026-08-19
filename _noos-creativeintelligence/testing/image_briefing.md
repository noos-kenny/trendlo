# Image Briefing per Template

The principle for ordering generated images against a template library. The template anatomies themselves (e.g. a client's M1–M7) are client-specific and live in the client's knowledge tree — this file is only the standard.

## Negative space is part of the template

Every template in a client's template library must have its **negative space documented**: where the text sits, and therefore where the image must stay clean. A brief's image instruction **must respect it**, stated in the generation prompt in plain spatial terms. House style:

> "The entire upper 40 percent of the frame is deliberately clean negative space for text overlay."

An image generated without the template's negative space in the prompt is a re-generation waiting to happen.

## Cost logic: background and copy are decoupled

One generated image carries **many** copy variants, languages and hooks — the text is laid on in Canva (`replace_text`), not baked into the image. Therefore:

- 3 concepts × 3 hooks × 2 languages = **18 variants requires 3–6 images, not 18.**
- Order images per **concept × template**, never per final variant.
- A new language or a new hook on an existing concept costs zero new images.

## Checklist for a brief's image order

1. Which template will each concept run in? (template ⇒ negative space ⇒ prompt constraint)
2. The client's refusal list as negative constraints (see `canva_creative_system.md`).
3. Number of images = concepts × backgrounds needed, after decoupling copy.
