name: Super Crafter
description: AI-powered design automation tool for generating and refining visual assets using advanced AI models
version: 1.0.0
author: OpenClaw Team
tags: design, ai, automation, generative
dependencies: openai-api, stable-diffusion-api, design-tools-sdk
env_vars: OPENAI_API_KEY, STABILITY_API_KEY, DESIGN_WORKSPACE_PATH
---

# Super Crafter

## Purpose

Super Crafter is an AI-powered design automation tool that leverages advanced generative AI models to create, refine, and iterate on visual design assets. It's designed for designers, developers, and content creators who need to rapidly prototype and generate high-quality visuals without starting from scratch.

### Real Use Cases
- **UI/UX Prototyping**: Generate wireframes, mockups, and interactive component designs for web/mobile apps
- **Brand Identity Creation**: Design logos, color palettes, typography schemes, and brand guidelines
- **Marketing Assets**: Create social media graphics, banners, and promotional materials with consistent branding
- **Icon and Illustration Generation**: Produce custom icons, illustrations, and visual elements for digital products
- **Style Guide Automation**: Generate comprehensive design systems with components, patterns, and documentation

## Scope

Super Crafter handles the full design lifecycle from concept to production-ready assets, focusing on AI-assisted creation rather than manual design work.

### Supported Commands
- `/craft-ui <description>` - Generate UI mockups and component designs
- `/craft-logo <brand> <style>` - Create logo variations for brands
- `/craft-palette <mood> <colors>` - Generate color schemes and palettes
- `/craft-icon <purpose> <style>` - Produce icons for specific use cases
- `/craft-illustration <theme> <elements>` - Create illustrations and graphics
- `/refine-design <asset_id> <feedback>` - Iterate on existing designs
- `/export-design <asset_id> <format>` - Export designs in various formats (SVG, PNG, PDF)

### Limitations
- Does not handle 3D modeling or complex animations
- Requires API access to AI services (OpenAI, Stability AI)
- Output quality depends on prompt specificity and AI model capabilities
- Not suitable for highly technical or engineering diagrams

## Work Process

### Step-by-Step Workflow

1. **Initialization**: Set up workspace and verify API connections
   ```bash
   openclaw super-crafter init --workspace /path/to/designs
   ```

2. **Asset Planning**: Analyze requirements and prepare detailed prompts
   - Gather reference materials and style guidelines
   - Define target dimensions, color constraints, and usage context
   - Research similar designs for inspiration

3. **AI Generation**: Execute crafting commands with specific parameters
   ```bash
   /craft-ui "Modern e-commerce product card with hover effects, 400x300px, clean minimal style"
   ```

4. **Refinement Loop**: Review and iterate on generated assets
   ```bash
   /refine-design asset_123 "Make the button more prominent and add subtle shadow"
   ```

5. **Quality Assurance**: Check design consistency and technical specs
   - Verify color contrast ratios for accessibility
   - Ensure scalability for different screen sizes
   - Validate brand guideline compliance

6. **Export and Integration**: Prepare final assets for use
   ```bash
   /export-design asset_456 --format svg --optimize
   ```

### Environment Setup
```bash
export OPENAI_API_KEY="your-openai-key"
export STABILITY_API_KEY="your-stability-key"
export DESIGN_WORKSPACE_PATH="/home/user/designs"
```

## Golden Rules

1. **Prompt Specificity**: Always provide detailed, specific prompts including dimensions, style references, and context to achieve better AI outputs
2. **Ethical Design**: Avoid generating content that could be harmful, discriminatory, or infringe on existing trademarks
3. **Iterative Refinement**: Use multiple refinement cycles rather than trying to perfect prompts on the first attempt
4. **Brand Consistency**: Maintain consistent visual language across related assets within a project
5. **Technical Constraints**: Consider practical limitations like file sizes, browser compatibility, and performance impact
6. **Originality Check**: Review outputs for unintentional similarities to existing designs and modify accordingly
7. **Accessibility First**: Ensure generated designs meet WCAG guidelines for color contrast and readability

## Examples

### UI Component Generation
**Input:**
```
/craft-ui "Dashboard card for user analytics showing metrics, charts, and actions. Use blue color scheme, modern flat design, responsive layout."
```

**Output:**
- Generated 3 variations of analytics dashboard cards
- Assets saved as: `analytics_card_v1.svg`, `analytics_card_v2.svg`, `analytics_card_v3.svg`
- Includes responsive CSS classes and hover states
- Color palette: Primary #007BFF, Secondary #6C757D, Background #FFFFFF

### Logo Design Refinement
**Input:**
```
/refine-design logo_089 "Simplify the icon, make text more legible, use warmer colors"
```

**Output:**
- Updated logo_089_v2.svg with simplified geometric shapes
- Changed font from Sans Serif to a more readable alternative
- Adjusted color scheme from cool blues to warm oranges (#FF6B35, #F7931E, #FFD23F)
- Maintained brand scalability from 32px to 512px

### Color Palette Creation
**Input:**
```
/craft-palette "Professional tech startup, trustworthy and innovative" 5
```

**Output:**
Generated palette with 5 colors:
- Primary: #2D3748 (Deep Navy)
- Secondary: #4299E1 (Bright Blue)
- Accent: #48BB78 (Green Success)
- Neutral: #F7FAFC (Light Gray)
- Warning: #ED8936 (Orange Alert)

Palette file: `tech_startup_palette.json` with hex codes, RGB values, and contrast ratios.

## Rollback Commands

### Asset Version Revert
```
/rollback-design <asset_id> --to-version <version_number>
```
Example: `/rollback-design ui_mockup_001 --to-version 2`

### Batch Asset Deletion
```
/cleanup-designs --project <project_name> --before-date 2024-01-01
```
Example: `/cleanup-designs --project ecommerce_redesign --before-date 2024-01-01`

### Workspace Reset
```
/reset-workspace --confirm-destructive
```
Warning: This removes all generated assets and cannot be undone.

## Verification Steps

1. **API Connectivity**: Run `/status` to verify AI service connections
2. **Asset Integrity**: Use `/validate-design <asset_id>` to check file corruption
3. **Brand Compliance**: Run `/check-brand <asset_id> <guidelines_file>` for consistency
4. **Performance**: Test export times and file sizes against requirements

## Troubleshooting

### Common Issues
- **Low Quality Outputs**: Increase prompt detail and use reference images
- **API Rate Limits**: Implement delays between requests or upgrade API plans
- **Inconsistent Styles**: Create and reference style guides in prompts
- **Large File Sizes**: Use `/optimize-export` flag for production assets
- **Color Inaccuracies**: Specify exact hex codes in prompts for brand colors

### Debug Commands
- `/debug-prompt <asset_id>` - Shows the exact prompt sent to AI
- `/performance-log` - Displays generation times and API usage
- `/error-details <error_code>` - Provides detailed error information