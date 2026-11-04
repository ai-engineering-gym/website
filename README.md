# AI Engineering Gym — Website

Public website for [ai-engineering-gym.com](https://ai-engineering-gym.com/), built with
[Hugo](https://gohugo.io/) and the [Hextra](https://github.com/imfing/hextra) theme
(v0.13.x, git submodule in `themes/`).

Deployed to GitHub Pages via the workflow in `.github/workflows/deploy.yml`
(Hugo 0.167 extended, submodule-aware checkout).

## Local development

```sh
git clone --recurse-submodules <this-repo>
cd ai-engineering-gym-website
hugo server   # needs Hugo >= 0.137 with extended (brew install hugo)
```

## Content map

| Path | Purpose |
|---|---|
| `content/_index.md` | Landing page (hero + value props) |
| `content/positioning/` | What the Gym is / isn't, open-core model |
| `content/benchmarks/` | Evidence: benchmark results and methodology |
| `content/university/` | University program (free, no paid seats) |
| `content/blog/` | Updates and engineering notes |

Contact address is configured once in `hugo.yaml` (`params.contact.email`) and
rendered by the `contact-cta` shortcode — change it there, not in pages.
