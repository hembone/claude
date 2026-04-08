# Claude Project

This repo is a workspace for developing skills and agents.

## Isolation Rule

Each top-level folder (`marketing-team/`, `artist/`, `shop/`, etc.) is a fully independent silo. They must not connect, communicate, or share agents, tools, data, or files with each other. An agent in one silo must never call an agent in another silo, read files from another silo, or reference another silo's resources. Keep all work scoped to the silo it belongs to.

## Project Structure

```
marketing-team/          — Agent-based marketing department
  agents/                — Agent definitions (markdown files)
    researcher.md        — Research agent for looking up market data, trends, competitors
    designer.md          — Visual media designer for marketing assets (Nano Banana Pro)
    writer.md            — Content writer for blog posts, ad copy, social captions, etc.
    brand-specialist.md  — Brand identity specialist for onboarding and defining brands
    publisher.md         — Publishes/schedules content to social media (Post Bridge)
  clients/               — Client brand identity files
    arcade-void/         — Arcade/retro gaming brand
    della-and-dale/      — Client brand
artist/                  — Standalone art agent (not tied to clients)
  artist.md              — Art-focused image generation
shop/                    — Shopping assistant skill (in progress)
```

## Marketing Team

### Agents

Agent definitions live in `marketing-team/agents/`. Each agent is a markdown file with YAML frontmatter (name, description, model, tools) and a system prompt body.

Available agents:
- **brand-specialist** — Guides clients through building their complete brand identity. Interviews the user, calls the researcher for market context and competitor branding, and fills out all brand files (brand guide, visual identity, voice and tone, etc.). Specializes in brand trends and innovative, forward-thinking design.
- **researcher** — Looks up any requested information while keeping the current client's brand identity in mind. Can be called by other agents when they need data to make decisions.
- **designer** — Creates visual marketing assets (Instagram posts/carousels, X posts, TikTok, Pinterest) using Nano Banana Pro via the Gemini API. References client brand identity, calls the researcher for context, and calls the writer when copy is needed for a design. Saves to client's `designs/` folder.
- **writer** — Creates written marketing content (blog posts, ad copy, social media captions, email copy, website copy). Writes in the client's voice, gathers info from the researcher agent when needed, and saves long-form content to the client's `content/` folder. Also provides copy to the designer on request.
- **publisher** — Publishes or schedules finished content to social media via Post Bridge. Supports Instagram, X, TikTok, Pinterest, YouTube, LinkedIn, Facebook, Threads, and Bluesky. Always confirms with the user before posting.

### Clients

Each client has a folder in `marketing-team/clients/` with these brand identity files:
- `brand-guide.md` — Mission, vision, values, story, tagline
- `voice-and-tone.md` — Writing style, tone, vocabulary
- `target-audience.md` — Personas, demographics, pain points
- `visual-identity.md` — Colors, typography, logo, imagery
- `messaging-framework.md` — Key messages, value props, positioning
- `content-guidelines.md` — Topics, pillars, platform rules
- `products-and-services.md` — Offerings, pricing, features
- `assets/` — Logos, fonts, images
- `examples/` — Sample content, past campaigns

### How to Use

When working on a marketing task:
1. Identify the client
2. Read their brand identity files first
3. Use the appropriate agent(s) for the task
4. Always pass the client name when invoking an agent

## Artist

The artist agent lives in `artist/artist.md`, separate from the marketing team. It creates original artwork and creative visuals, is not tied to any client or brand, does its own web research for references and inspiration (does not use the researcher agent), and accepts reference images from the user and prompts for where to save artwork.
