---
title: Flash Bootloader RH850 GM docs
description: Documentation home for the GM SLP6 flash bootloader on Renesas RH850
template: splash
hero:
  tagline: AUTOSAR flash bootloader for GM SLP6 on Renesas RH850 (Vector SIP CBD1500635)
  actions:
    - text: Getting started
      link: ./getting-started/
      icon: right-arrow
    - text: Module overview
      link: ./modules/
      icon: open-book
      variant: secondary
---

import { Card, CardGrid } from '@astrojs/starlight/components';

## What is this?

This site documents a **GM SLP6 flash bootloader** for the **Renesas RH850
(P1M R7F701363)** — UDS over CAN, GM container/kompression handling, secure
verification (SHA-256 / RSA), an FBL updater, and the demo/integration glue
around it. The repository is a **Vector Software Integration Package (SIP)**
delivery (`CBD1500635`, SIP `06.04.03`, GHS `2015.1.7`).

<CardGrid>
  <Card title="AUTOSAR layers" icon="layers">
    How the tree maps to ASW, CDD, BSW Services, ECU Abstraction, MCAL and
    integration. See [AUTOSAR layers](./autosar-layers/).
  </Card>
  <Card title="Vector vs. custom" icon="puzzle">
    Which files are Vector-provided, which are third-party (Renesas,
    cryptovision, GNU/Cygwin), and which are integration-owned.
    See [origin policy](./vector-vs-custom/).
  </Card>
  <Card title="SIP delivery" icon="package">
    Delivery readme, test/issue reports and version map (`v_ver.h`).
    See [SIP](./sip/).
  </Card>
  <Card title="Converted PDFs" icon="document">
    All `Doc/` and tool PDFs converted to Markdown under
    [General](./general/) and the matching module pages.
  </Card>
</CardGrid>

## Assumptions stated up front

- The whole repository **is** the SIP. There is no separate `SIP/`
  subfolder, so `sip/` in these docs is a *view* over the same tree
  (delivery `CBD1500635`, package `FBL GM SLP6`, micro `RH850 P1M`).
- No `.doc`/`.docx` files were found; the `Doc/` tree contains only PDFs
  plus one HTML delivery description and one XML issue report. All PDFs
  were converted; `.doc/.docx` handling is therefore documented as
  not-applicable rather than skipped.
- `docs/` is an **Astro Starlight** project (most popular Astro docs
  theme), not Jekyll. Sidebar/navigation is configured in
  `astro.config.mjs`, front matter is Starlight (`title`/`description`/
  `sidebar`), and content lives under `src/content/docs/`. This supersedes
  the Jekyll `_config.yml` / `layout+parent+nav_order` sketch in the task
  brief, which does not apply to Astro.
- No username or repository name is hard-coded anywhere, so forks keep
  working. The Pages `base` comes from `PAGES_BASE` (set it to
  `/<repository-name>/` in your own Pages workflow).

[Back to top](#top)
