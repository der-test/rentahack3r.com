# Copilot Instructions - Rent a Hack3r

## Project Overview

This is a **satirical/joke website** built with Jekyll using the GitHub Pages Hacker theme. The site parodies fraudulent "hacker for hire" services with humorous fictional content about illegal activities. It is **not a real service** and exists purely for entertainment and educational purposes.

**Key point**: All content is intentionally comedic and fictional. Do not treat any "service offerings" as real.

## Architecture

### Jekyll-Based Static Site
- **Theme**: `pages-themes/hacker@v0.2.0` (remote theme)
- **Build System**: Jekyll (GitHub Pages)
- **Configuration**: `_config.yml` - minimal setup with theme and plugin configuration
- **Entry Point**: `README.md` - serves as the main page content when built

### File Structure
```
/
├── README.md                    # Main content (rendered as index.html by Jekyll)
├── _config.yml                  # Jekyll configuration
├── _includes/head-custom.html   # Custom head injection (adds custom CSS)
├── assets/css/custom.css        # Style overrides
├── qr/qr.html                   # Standalone HTML page (German security warning)
└── CNAME                        # Custom domain configuration
```

## Critical Conventions

### Content Strategy
- **Satire-First**: All text, testimonials, and "case studies" are fictional humor
- **Juxtaposition Humor**: Treats impossible/illegal requests as if serious, then deflates with jokes
- **Disclaimer Pattern**: Always includes explicit disclaimers that the site is fictional and not for illegal activity use
- **Terminal/Hacker Aesthetic**: Content styled as command-line interactions and system messages (`$ ` prompts, `[STATUS]` blocks, code fences)
- **Glitch Art Visual**: ASCII art decorations, terminal box drawing characters, intentional "data corruption" styling

### Visual Redesign: Glitch Art CRT Green
The site now features an immersive **glitch art aesthetic** with retro CRT terminal vibes:

**Color Palette**:
- Primary: CRT green `#00ff41` with glow effects
- Accents: Magenta `#ff10f0`, Cyan `#00ffff` for RGB channel separation
- Background: Dark navy `#0a0e27` simulating old monitor glow

**CSS Effects** (in `assets/css/custom.css`):
- **Scanline overlay**: Fixed position horizontal stripe pattern with `repeating-linear-gradient` for CRT effect
- **Animated glitch**: Headers shift between green/cyan/magenta with RGB channel separation (`glitch-color-shift` keyframes)
- **Text shadow glow**: All headers have `text-shadow` with multiple layers for neon glow
- **Service cards** (`.service-item`): Colored borders (green/magenta/cyan) with hover transform effects
- **Corrupted sections** (`.corrupted`): Gradient background with `[CORRUPTED DATA]` label and pulsing animation
- **Terminal boxes** (`.response-box`): Dark background with green borders and `$ ` prefix
- **Disclaimer** (`.disclaimer`): Dashed magenta border with animated glitch color cycling

**Animation Strategy**:
- Headers: Continuous `glitch-color-shift` (8-15s duration) for subtle shifting color effect
- Hover states: `glitch-intense` animation (0.3s) creates jarring displacement on interaction
- CRT flicker: Body-wide 0.15s opacity flicker for authentic old monitor feel
- Scanlines: Fixed, no animation - always visible overlay

### Multilingual Content
- `qr/qr.html` contains German text ("Dieses USB-Gerät wurde als Test in ihrem Gerät hinterlassen...")
- Indicates possible EU/German audience awareness or cross-cultural humor elements

## Modification Guidelines

When updating content:

1. **Preserve the satirical tone** - All additions should be clearly humorous and impossible/illegal in nature
2. **Add disclaimers** - Any new "service" description should be followed by a joke or explicit statement that it's fictional
3. **Keep disclaimers prominent** - The repeated disclaimer that "this is not real" is intentional and shouldn't be removed
4. **Maintain glitch aesthetic** - New content should include terminal-style formatting: code blocks with `$` prompts, `[STATUS]` blocks, ASCII art borders
5. **Apply CSS classes appropriately**:
   - `.service-item`: For service descriptions (auto-applies borders and hover effects)
   - `.corrupted`: For sections that should appear "data-corrupted" with animated label
   - `.response-box`: For terminal output/responses with prompt prefix
   - `.disclaimer`: For legal disclaimers (auto-applies magenta border and glitch animation)
6. **Keep HTML inline in README**: Use `<div>` blocks with CSS classes directly in markdown for consistent styling
7. **Test with Jekyll locally** - Run `bundle exec jekyll serve` to preview glitch animations and scanline effects before pushing (requires Ruby/bundler)

## Build & Deployment

- **Platform**: GitHub Pages
- **Build Trigger**: Push to main branch (automatic)
- **Custom Domain**: Configured via `CNAME`
- **No build steps required** - Jekyll handles compilation automatically

## Known Patterns

- **Procedural humor** - Section structure (Services → How It Works → Testimonials → Disclaimers) mirrors real service site structure but with absurdist elements
- **First-person mock engagement** - Text like "Imagine sending us an email..." treats fictional processes as if real
- **Responsive disclaiming** - FAQ section preemptively addresses legality concerns with jokes rather than avoiding the topic

## Common Tasks

- **Update main content**: Edit `README.md` (markdown rendered as homepage)
- **Adjust styling**: Modify `assets/css/custom.css`
- **Add multilingual content**: Add new HTML files in appropriate folders, following `qr.html` pattern
- **Change theme**: Update `remote_theme` version in `_config.yml`
