# CLAUDE.md

## Auto-learned Rules

<!-- claude-evolve:managed-start -->

<!-- claude-evolve:rule id=r_mqcxxtsu_l42s score=5.4 created=2026-06-13 source=observation complexity=simple -->
- After taking a Playwright screenshot, immediately search for the file in known output locations (~/.playwright-mcp/, ~/Desktop, ~/) using find with -newermt before assuming the path
<!-- /claude-evolve:rule -->

<!-- claude-evolve:rule id=r_mqcxxtto_70k9 score=5 created=2026-06-13 source=observation complexity=simple -->
- After git push, poll GitHub Pages deployment status via GitHub API (repos/{owner}/{repo}/pages/builds or deployments) in a loop before opening Playwright to verify — do not navigate immediately after push
<!-- /claude-evolve:rule -->

<!-- claude-evolve:rule id=r_mqcxxtuh_kizr score=5.4 created=2026-06-13 source=observation complexity=simple -->
- When verifying a deployed UI change with Playwright, use browser_evaluate to programmatically trigger the UI state (open lightbox, wait for image swap) before taking a screenshot — do not screenshot the idle page
<!-- /claude-evolve:rule -->

<!-- claude-evolve:rule id=r_mqcxxtv6_2l9r score=5.4 created=2026-06-13 source=observation complexity=simple -->
- Clean up temporary artefact files (screenshots, debug crops) at the end of the session in the same Bash call as log inspection
<!-- /claude-evolve:rule -->

<!-- claude-evolve:rule id=r_mqcxxtvu_5m5s score=5.1 created=2026-06-13 source=observation complexity=simple -->
- Use ToolSearch select: to load only the specific Playwright MCP tool schemas needed for the task before calling them
<!-- /claude-evolve:rule -->

<!-- claude-evolve:rule id=r_mqcxxtwj_dpjf score=5.1 created=2026-06-13 source=anti_pattern complexity=simple -->
- Do not Edit an HTML file multiple times in rapid succession without a Read in between — read the current file state first to avoid context drift across edits
<!-- /claude-evolve:rule -->

<!-- claude-evolve:rule id=r_mqcxxtx8_t2qj score=5.4 created=2026-06-13 source=anti_pattern complexity=simple -->
- When saving a Playwright screenshot to a custom filename, verify the MCP tool's actual output directory before the call (check docs or prior session notes) — do not assume the file lands in a predictable location and then search for it reactively
<!-- /claude-evolve:rule -->

<!-- claude-evolve:rule id=r_mqczzbdx_aeb8 score=5 created=2026-06-13 source=observation complexity=simple -->
- Always call browser_close before the final cleanup Bash call — ensures browser releases file handles before rm runs
<!-- /claude-evolve:rule -->

<!-- claude-evolve:rule id=r_mqczzbem_z2h7 score=5 created=2026-06-13 source=observation complexity=simple -->
- When verifying a deployed binary asset (image, font, etc.), capture its local size with stat -f%z and poll the remote Content-Length until they match before opening Playwright — avoids verifying a stale CDN-cached version
<!-- /claude-evolve:rule -->

<!-- claude-evolve:managed-end -->
