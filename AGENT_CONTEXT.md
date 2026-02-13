# Antigravity Base Theme - Agent Context

**SYSTEM INSTRUCTION: READ THIS FILE FIRST BEFORE MODIFYING THE THEME.**

## Overview
This is a high-performance, modular Shopify Online Store 2.0 theme designed as a foundation for future projects. Ideally, you should maintain its structure and design patterns when making modifications.

## Architecture
- **Global Settings**: Defined in `config/settings_schema.json`. Use `settings.color_text`, `settings.type_header_font`, etc.
- **CSS Variables**: Mapped in `layout/theme.liquid`. Use `var(--color-text)`, `var(--page-width)`, `var(--grid-gap)` into your CSS.
- **Atomic Styles**: Located in `assets/base.css`. Use `.page-width`, `.grid`, `.btn` for consistency.

## Design Patterns for New Sections
When creating a new section, follow this template:

1.  **Liquid Structure**:
    ```liquid
    {%- style -%}
      .section-{{ section.id }} {
        padding-top: {{ section.settings.padding_top }}px;
        background: {{ section.settings.bg_color }};
      }
    {%- endstyle -%}
    <div class="section-{{ section.id }} page-width">
       <!-- Content -->
    </div>
    ```

2.  **Schema Requirements**:
    - Always include `presets` so the section is usable in the Theme Editor.
    - Always include `padding_top` and `padding_bottom` range settings.
    - Use `blocks` for repeating content (columns, slides, features).

3.  **Naming**:
    - Use kebab-case for filenames (e.g., `featured-product.liquid`).
    - Use clear, capitalized names in Schema (e.g., "Featured Product").

## Key Files
- `layout/theme.liquid`: Main entry point.
- `sections/header.liquid`: Global header.
- `sections/footer.liquid`: Global footer.
- `assets/base.css`: Utility classes.

## How to Customize
1.  **Check Settings First**: Before writing CSS, check if a global setting exists in `config/settings_schema.json`.
2.  **Extend Schema**: If a user wants to change a color or size, add it to the section's `schema` settings rather than hardcoding it.
3.  **Use CSS Variables**: Always use the defined CSS variables for colors and fonts to ensure the theme settings work.

## Prompt Implementation
To load this context into a new agent session, the user should provide the path to this file or paste its content.

**"I am working on the Antigravity Base Theme. Please review `AGENT_CONTEXT.md` to understand the architecture and style guidelines before proposing changes."**
