<div align="center">

# personal-taste

**Retro-futurism, distilled into a frontend taste — for an AI.**

`English` · [简体中文](./README.zh.md)

</div>

![Dark retro-futurism sample landing page](./assets/sample-hero.png)

> Give an AI **my** taste, not the average of everyone's.

This is an Agent Skill for [Claude Code](https://claude.com/claude-code): a portable file of design rules. Whenever an AI builds or redesigns a frontend for me, it follows this taste automatically — instead of collapsing into the templated, purple-gradient "AI slop" that every model drifts toward by default.

## Design philosophy — retro-futurism

Imagine the future using the materials and craft of the 20th century. Three pillars:

- **Monumentality** — heavy, grounded, vertical grandeur.
- **Analog materials** — texture comes from concrete, ink, halftone, film, paper; never from digital gloss.
- **A constructed world** — everything is designed and translated (illustration, silhouette, monochrome wash) before it earns a place on screen; unprocessed "reality" stays out.

One phrase runs through all of it: **one light in the dark.** A page gets exactly one glowing focal point — or one saturated accent — and everything else recedes. Its sworn enemy is the opposite: the "everywhere-glowing" sci-fi-dashboard look.

## What it governs

| Aspect | In one line |
|---|---|
| Color | No color beats bad color; when used, one hue floods the page like ambient light. Black is structure, white is light. |
| Light | A single, scarce light source is the focal point; glow is allowed but must be rare. |
| Layout | Big masses, silhouette-first, asymmetric; right angles, only sculptural curves. |
| Texture | Matte by default — aged print, halftone dots, film grain, line engraving. |
| Type | Two poles — heavy display (loud) and copperplate / cold serif (ornate). The enemy is neutral sans as the lead. |
| Imagery | No documentary photos; only illustration, sketch, or heavily-treated images. |
| Motion | The Tarantino rule — stillness as default, motion decisive. No floating easing. |

Full rules in [`SKILL.md`](./SKILL.md).

![Nude-concrete craft and type specimen](./assets/sample-craft.png)

## How to use

**As a Claude Code skill:**

```bash
git clone https://github.com/bot-Ethan/personal-taste-skill.git ~/.claude/skills/personal-taste
```

Claude triggers it automatically when building frontends.

**With any other AI:** paste the contents of [`SKILL.md`](./SKILL.md) into the conversation.

## Where it came from

This taste wasn't written from thin air — it was **distilled** from cross-medium references:

- **Architecture** — Tadao Ando's Church of the Light, Peter Zumthor's new LACMA
- **Comics** — 20th-century Batman (BTAS / Dark Deco), the aged print of old Transformers covers
- **Film** — the complete works of Quentin Tarantino, *American Psycho*
- **Album art** — A$AP Rocky's film-grain retro, Drake's copperplate wordmarks

Distilling across media keeps the result distinctive — it won't "look like some website."

## Acknowledgements

Inspired in spirit and structure by [taste-skill](https://github.com/Leonxlnx/taste-skill), an open-source frontend skill that fights "AI slop." This repo is its *personal* fork: not aiming for universally good taste, only for **mine**.

## License

[MIT](./LICENSE)
