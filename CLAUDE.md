# CLAUDE.md

## Auto-learned Rules

<!-- claude-evolve:managed-start -->

<!-- claude-evolve:rule id=r_mqcxxtuh_kizr score=5.1 created=2026-06-13 source=observation complexity=simple -->
- When verifying a deployed UI change with Playwright, use browser_evaluate to programmatically trigger the UI state (open lightbox, wait for image swap) before taking a screenshot — do not screenshot the idle page
<!-- /claude-evolve:rule -->

<!-- claude-evolve:rule id=r_mqcxxtwj_dpjf score=5.5 created=2026-06-13 source=anti_pattern complexity=simple -->
- Do not Edit an HTML file multiple times in rapid succession without a Read in between — read the current file state first to avoid context drift across edits
<!-- /claude-evolve:rule -->

<!-- claude-evolve:rule id=r_mqd18xsn_tt5t score=5.3 created=2026-06-14 source=observation complexity=simple -->
- After multiple rapid Edits to a single HTML file, run a python3 inline grep check (grep for key identifiers + feature flags) before launching the browser — catches context drift without a full Read
<!-- /claude-evolve:rule -->

<!-- claude-evolve:rule id=r_mqd18xtc_89eu score=5 created=2026-06-14 source=observation complexity=simple -->
- After local Playwright verification passes, commit and push in the same Bash block, then immediately poll the live GitHub Pages URL with curl + cache-buster until the new identifier appears — do not assume push equals live
<!-- /claude-evolve:rule -->

<!-- claude-evolve:rule id=r_mqd18xu2_gbbj score=5.3 created=2026-06-14 source=observation complexity=simple -->
- After Playwright screenshot verification, close the browser and clean up temp screenshot files and the HTTP server in a single Bash block before committing — never leave orphaned processes or temp files
<!-- /claude-evolve:rule -->

<!-- claude-evolve:rule id=r_mqd18xur_uzoy score=5 created=2026-06-14 source=observation complexity=simple -->
- When adding a touch/mobile-visible feature (e.g. hover:none delete button), verify both the CSS rule presence AND the rendered UI via Playwright screenshot before committing — grep alone is insufficient
<!-- /claude-evolve:rule -->

<!-- claude-evolve:rule id=r_mqd18xvg_rtaw score=5.3 created=2026-06-14 source=anti_pattern complexity=simple -->
- Do not perform 8 sequential Edits to the same HTML file without a Read between the first and last edit — after 4+ edits, Read the file to confirm accumulated state before continuing
<!-- /claude-evolve:rule -->

<!-- claude-evolve:managed-end -->
