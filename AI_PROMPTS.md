# AI Prompt Library for Cakes.dk

## 1. Cake Concept Generation
System: You are a professional Danish pastry chef and food copywriter. Output structured JSON only.
User: Generate 12 innovative Danish cake concepts for {occasion}. Each: name, one_line_hook (<=18 Danish words), primary_flavors (array), texture_descriptors (array), difficulty (easy|medium|advanced), seasonal_fit (array), suggested_tags (array), uniqueness_score (1–10). Focus on {constraints}. No duplication.

## 2. Recipe Draft
System: Expert baker; enforce safe temperatures and metric units.
User: Draft a detailed recipe for: {concept}. Include: intro (≤60 words), ingredients grouped, precise gram weights, numbered steps (≤14), timing (prep, bake, rest), difficulty, plating suggestion, allergen list, 2 variation ideas, storage advice. Return valid Markdown with front matter fields.

## 3. Variation Expansion
User: Provide 5 variations of this base recipe (JSON). Input recipe (YAML): ```{recipe_yaml}```. Each variation: name, modified_ingredients (diff list), changed_steps (map step_number -> new text), flavor_rationale.

## 4. Pan Size Scaling
User: Adjust this recipe from {original_diameter} cm round pan to {target_diameter} cm. Output new ingredient weights (grams), rounded (except leavening). Warn if eggs fractioned.

## 5. Dietary Conversion
User: Convert this recipe to gluten-free and lactose-free while keeping texture. Provide substitution mapping, justification, expected texture change.

## 6. Ingredient Constraint Query
User: I have: {pantry_list}. I can buy {max_new} new items. Suggest 3 cake ideas. Each: missing_items, difficulty, why_it_works, allergen_flags.

## 7. Decoration & Styling
User: Suggest 4 minimalist Scandinavian decoration concepts for: {concept}. Each: style_name, color_palette (hex), garnish_elements, positioning_notes, photo_setup.

## 8. Image Generation Prompt Template
Close-up, Scandinavian minimalist cake: {adjectives}, {cake_type} with {primary_flavors}, styled with {decoration}, soft natural window light, shallow depth of field, neutral matte ceramic plate, 45 degree angle, crisp frosting texture, high-resolution food photography. Negative: people, hands, text, watermark, logo, low quality, oversaturated.

## 9. Tag Normalization
User: Normalize tags to controlled vocabulary (list: {controlled_list}). For each original: normalized, confidence, reason, needs_review (bool).

## 10. Trending Insights
User: Given view stats JSON: {stats_json} identify: emerging_flavor_themes (≤5), rising_tags (≤5), recommended_content_gaps (≤5).

## 11. Bilingual Translation
User: Translate Danish to English preserving tone: ```{danish_text}```. Output table (Danish, English).

## 12. Safety & Allergen Check
User: Analyze ingredient list: {ingredients}. Output: allergens (EU list), raw_egg_warning (if applicable), concise safety_note.

---
This file evolves as features grow. Keep prompts atomic & testable.
