# Ledger Sherlock — Design Direction

## Approach 1
**Theme Name:** Evidence Ledger

**Very Brief Intro:** A quiet, editorial fintech system that treats every number as a traceable piece of evidence. Creamy paper tones, ink-like typography, and one signal color make investigation feel deliberate and trustworthy.

**Probability:** 0.07

## Approach 2
**Theme Name:** Control Room Mint

**Very Brief Intro:** A crisp operations console built around cool mint surfaces and precise status instrumentation. It feels fast, technical, and highly legible without becoming sci-fi.

**Probability:** 0.03

## Approach 3
**Theme Name:** Carbon Signal

**Very Brief Intro:** A dark, high-contrast command center where exception risk is surfaced through bright signal colors and subtle glow. It is decisive and intense, designed for teams living in the queue.

**Probability:** 0.09

## Selected Direction: Evidence Ledger

### Design Movement
Contemporary editorial modernism: the restraint of Swiss information design combined with the material cues of a case file and the calm precision of premium financial infrastructure.

### Core Principles
1. **Evidence before decoration:** every visual treatment should clarify status, provenance, or next action.
2. **Quiet confidence:** wide breathing room, restrained borders, and almost no ornament keep the interface calm under financial pressure.
3. **Signal, not spectacle:** use one ownable citron accent for focus and disciplined semantic colors for success, warning, and failure.
4. **Structured asymmetry:** align content to an operational rail with offset panels and evidence columns instead of a generic centered dashboard grid.

### Color Philosophy
The base is warm paper (#F6F5F1) and soft white (#FFFEFC), chosen to make long investigation sessions feel less clinical than blue-white SaaS screens. Ink charcoal (#18221F) creates authority and high reading contrast. A distinctive citron-lime signal (#C4D82E) marks active investigation and primary actions: it reads like a highlighter stroke over an audit document. Sage confirms a clean match; amber and terracotta reserve urgency for exceptions.

### Layout Paradigm
A persistent left evidence rail anchors navigation, while the main canvas uses a 12-column operational field: broad content on the left, a narrower "signal stack" on the right. The overview leads with a status sentence and action cluster, then offsets KPI cards, a reconciliation run panel, and a review queue. Dense tables are wrapped in spacious frames and use horizontal scrolling on small screens.

### Signature Elements
- **Case-file index rail:** a slim lime index bar on the active nav item and tiny uppercase section labels that feel like file tabs.
- **Evidence stamps:** compact outlined chips with mono IDs, source marks, and confidence states.
- **Signal bands:** thin horizontal progress/risk bands that replace oversized decorative charts.

### Interaction Philosophy
Actions should feel bounded and reversible. Primary actions visibly confirm intent with a pressed state and toast; navigation swaps the main canvas without losing the global rail. Exception rows expose a clear investigation affordance, and filters update the review queue immediately. Placeholder actions say what is coming instead of pretending to perform a real backend operation.

### Animation
Use short, physical transitions: cards enter with a 180ms upward settle and 24ms stagger; active rail markers slide 160ms with a sharp ease-out; progress bands animate only when a reconciliation run starts; drawers and detail panels use 220ms opacity + translate transitions. Never animate layout dimensions or use a full-page spinner. Respect reduced motion.

### Typography System
Use **DM Sans** for UI, body copy, and labels; pair it with **IBM Plex Mono** for record IDs, metric numerals, timestamps, and system metadata. Headlines use DM Sans 650 with tight tracking; section labels use 11px uppercase mono with 0.12em tracking; body text stays 14–15px with generous line-height. This creates a calm editorial hierarchy without using Inter.

### Brand Essence
**Ledger Sherlock is the calm investigation layer for finance teams who need every mismatch explained before it moves money.**

Personality adjectives: **precise, composed, forensic**.

### Brand Voice
Headlines are concise and observational; CTAs are specific and bounded; microcopy names the evidence instead of using vague growth language.

Example lines:
- **“Every mismatch leaves a trail.”**
- **“Review the 12 records that still need a human call.”**

### Wordmark & Logo
The mark is a simple square ledger sheet with two offset horizontal rules and a magnifying-glass loop cut into the lower-right corner. The wordmark is a custom lockup: “Ledger” in DM Sans semibold, “Sherlock” in IBM Plex Mono medium with a small citron square replacing the dot between the words. The icon is designed to read clearly at 20px in the sidebar and 32px in the product header.

### Signature Brand Color
**Signal Citron — #C4D82E.** It is an ownable highlighter color: energetic enough to guide the eye, restrained enough to keep the finance UI serious.

## Style Decisions
- Keep the product light and paper-toned; do not introduce a dark-mode visual treatment in the first delivery.
- Use citron only for active navigation, primary actions, focus rings, and investigation emphasis.
- Use warm surfaces and ink text rather than cool gray defaults.
- Treat tables and metrics as evidence artifacts with clear provenance, not decorative dashboard tiles.
- Preserve the “Reconcile faster. Investigate smarter.” positioning in the product header and metadata.
- KPI cards use compact batch/source provenance stamps and thin signal bands, so they read as auditable evidence objects rather than generic dashboard tiles.

## Dark-mode refinement direction

- Use an original **Midnight Ledger** system: near-black blue-green canvas, layered graphite surfaces, muted slate text, and a restrained electric-lime signal accent.
- Draw only high-level inspiration from modern finance and command-workspace products: dense but calm navigation, a highly visible quick command surface, clear action hierarchy, and stateful operational cards. Do not reproduce another brand's layout, copy, or assets.
- Preserve Ledger Sherlock's forensic identity with evidence metadata, source-to-rule-to-human-gate progression, and warm status tones for exceptions rather than turning the app into a generic neon dashboard.

## Concise workspace direction

- Adopt the high-level principle of one primary task per page: a large single status headline, one primary action, one secondary action, and a compact context rail.
- Reduce parallel dashboards and decorative metrics. The initial visible canvas should lead with the reconciliation command, a short source-status strip, and only the exceptions that need attention.
- Use a low-noise black canvas with one signature lime action state, thin graphite dividers, compact metadata, and intentional empty space. Keep Ledger Sherlock’s own mark, copy, data model, and evidence-chain language.
