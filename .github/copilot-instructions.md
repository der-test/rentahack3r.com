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
- **Chaotic Navigation**: Headers are clickable links that form a circular navigation loop between sections, creating intentional disorientation
- **Non-Existent Contact**: Email uses fake non-existent TLD (`.nil`) to reinforce fiction while maintaining hacker aesthetic
- **No Spoilers**: User-facing text doesn't reveal the satirical nature—visitors discover the joke through exploration

### Visual Design: Extreme CRT Chaos
The site features an immersive **retro CRT terminal aesthetic** with extreme animated effects designed to feel chaotic and hyperstimulating:

**Color Palette**:
- Primary: CRT green `#00ff41` with pulsing glow effects
- Accents: Magenta `#ff10f0`, Cyan `#00ffff` for RGB channel separation
- Extended: Neon lime `#39ff14`, Acid green `#10ff10` for color cycling
- Background: Dark navy `#0a0e27` simulating old monitor phosphor

**CSS Animation Architecture** (in `assets/css/custom.css`):
- **Scanline overlay**: Animated repeating horizontal stripes with shifting effect (0.08s cycle)
- **Screen noise**: Fixed SVG noise overlay with continuous shift animation
- **Body flicker**: Global 0.05s opacity flicker simulating CRT instability
- **Full-screen glitch**: Body skew and color cycling (3s duration) affecting all text
- **Header animations** (h1-h6): Multiple simultaneous animations:
  - `glitch-color-chaos`: Ultra-aggressive 6-color cycling (3-5s)
  - `chromatic-pulse`: RGB channel separation with drop-shadow
  - `header-glow-shift`: Brightness and glow cycling
  - h1: Additional `h1-distort` for scale/skew wobble (1.5s)
  - h2: Additional `h2-pulse` and `h2-rotate` for layered effects
  - h3: `h3-wiggle` for continuous horizontal jitter (0.8s)
- **Link animations**: Pulsing text-shadow (`link-throb`, 1.5s) + continuous gradient shift in ::before pseudo-element
- **Service cards** (`.service-item`): Four simultaneous animations:
  - `card-pulse`: Shadow intensity pulsing (2s)
  - `card-border-shift`: Border color cycling between green/magenta/cyan (3s)
  - `card-glitch`: Micro-translations (4s)
  - Mobile: Additional `mobile-card-shake` for aggressive 0.6s jitter
- **Blockquotes**: Dual animations with color-shifting borders and opacity flicker
- **Code blocks**: Continuous `code-flicker` (0.5s opacity cycle) simulating transmission errors
- **List items**: Color cycling between green and neon-lime (6s)
- **Tables**: Row hover with skew transform + brightness filter
- **Emphasis elements**: 
  - `<strong>`: Dual `strong-pulse` and `strong-blink` (1.5s and 2s)
  - `<em>`: Dual `em-pulse` and `em-shimmer` brightness (2s and 3s)
- **Corrupted sections** (`.corrupted`): Pulsing opacity with glitch-chaos animation on `::before` label
- **Response boxes** (`.response-box`): Pulsing box-shadow (2s) with green glow intensification
- **Disclaimer** (`.disclaimer`): `glitch-color-chaos` color cycling (2s) + spinning `⚠️` emoji

**Mobile-Specific Enhancements**:
- Headers animate much faster (0.8-2s cycles instead of 3-5s)
- Service cards get `mobile-card-shake` aggressive jitter overlay
- Scanlines animate faster with increased opacity (0.2 instead of 0.12)
- Noise shift runs at 0.15s instead of 0.3s
- All link/text animations compressed to 1-1.5s cycles
- Tables get additional `table-distort` skew animation
- Mobile creates overlapping animation layers for cumulative chaos effect

**Accessibility**:
- All animations respect `prefers-reduced-motion` media query
- Critical content (disclaimers) remain readable despite effects
- Color isn't the only visual indicator (glyphs, icons, text present)

### Multilingual Content
- `qr/qr.html` contains German text ("Dieses USB-Gerät wurde als Test in ihrem Gerät hinterlassen...")
- Indicates possible EU/German audience awareness or cross-cultural humor elements

## Modification Guidelines

When updating content:

1. **Preserve the satirical tone** - All additions should be clearly humorous and impossible/illegal in nature
2. **Don't spoil the joke** - Avoid explicit mentions of "satire," "joke," or "fake" in user-facing text; let visitors discover it
3. **Add disclaimers** - Any new "service" description should be followed by a joke or explicit statement that it's fictional
4. **Keep disclaimers prominent** - The repeated disclaimer that "this is not real" is intentional and shouldn't be removed
5. **Maintain hacker aesthetic** - New content should include terminal-style formatting: code blocks with `$` prompts, `[STATUS]` blocks, ASCII art borders
6. **Use circular navigation** - New headers should link to other headers via markdown anchor links to create a chaotic navigation loop
7. **Non-existent contact info** - Contact details (email, phone) should use obviously fake/non-existent values (TLDs like `.nil`, domains that don't resolve)
8. **Apply CSS classes appropriately**:
   - `.service-item`: For service descriptions (auto-applies borders, color cycling, pulsing animations)
   - `.corrupted`: For sections that should appear "data-corrupted" with animated label and flicker
   - `.response-box`: For terminal output/responses with `$ ` prompt prefix and pulsing glow
   - `.disclaimer`: For legal disclaimers (auto-applies magenta border, color cycling, warning emoji)
9. **Keep HTML inline in README**: Use `<div>` blocks with CSS classes directly in markdown for consistent styling
10. **Test responsively** - Run `bundle exec jekyll serve` and test on mobile; animations are more aggressive on smaller screens
11. **Don't remove animations** - The extreme effects are intentional; they reinforce the chaotic hacker aesthetic

## CSS Classes Reference

- **Headers with links**: Wrap header text in markdown bracket syntax to make entire header clickable
- **Anchor navigation**: Use `<a name="section-id"></a>` before headers to create jump targets
- **Service item styling**: `<div class="service-item">content</div>` - applies pulsing borders, glow, scan sweep, color cycling
- **Corrupted data effect**: `<div class="corrupted">content</div>` - applies flicker, border cycling, glitch label
- **Terminal responses**: `<div class="response-box">output</div>` - applies dollar sign prefix, pulsing shadow
- **Legal disclaimers**: `<div class="disclaimer">text</div>` - applies dashed border, color chaos, spinning warning icon

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
