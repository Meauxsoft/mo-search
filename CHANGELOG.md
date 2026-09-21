# Mo-Search release history

Mo-Search has been in continuous development since 2005. This changelog documents released versions through **26.0**; work in progress for a future release is not listed here.

Generated from the Meauxsoft release history by `build-changelog.ps1`. Do not edit by hand.

## 26.0 — 2026, Sep 21

_A 40-day trial, a $50 license, and MoContext on this PC_

- Version: Public version is 26.0 (calendar year.release). Later 26.x and 27.0 update in place on the same install folders and exe name. 9.50 remains a separate installed product.
- Trial: 40-day trial of the full product, not a reduced build.
- License: $50 buys a 365-day license. Paddle emails an MS1. key to the buyer to paste in the app. Not a subscription.
- Buy: In-app and website Buy paths open Buy_MoSearch.html. 9.x donate / MOS9V codes do not license 26.0.
- MoContext: Ships with Mo-Search as the local MCP server. Compatible AI clients search and read from the Mo-Search index on this PC; nothing is uploaded.
- MoContext: Settings backup/restore, daily auto-backup, and a first-run choice to Restore or Start fresh. Default backup folder is Documents\MoBackups.
- Updates: AppUpdater downloads the installer over HTTPS and requires a valid Authenticode signature before apply.
- Search Home: Search Home, Simple Search counts, and Buy chrome share one layout so the combo, brand, and history cannot drift.
- Search: Text * ? ^ wildcards work in the search box without hanging the results list.
- MoVault: Private vault on this PC is coming soon. It is not included as a download with Mo-Search 26.0.

## 9.50.8 — 2026, Jul 17

_Safer duplicates, dependable indexing, and richer MoContext memory_

- Find Duplicates: Prevents hangs when file-type information is requested before the search database is ready.
- Find Duplicates: Handles large same-size groups more efficiently while still confirming every duplicate with a full comparison.
- Find Duplicates: Correctly compares files when Ignore Whitespace is enabled, including useful content that spans multiple read buffers.
- Find Duplicates: Stops treating files as duplicates if their lengths change while a comparison is running.
- Find Duplicates: Improves locked-file reporting, cancellation statistics, failed recycle visibility, and progress cleanup when closing.
- Find Duplicates: Supports file actions on UNC network paths without relying on drive-letter assumptions.
- File walking: Skips junctions and symbolic links so the same physical files are not scanned or offered for cleanup through alternate paths.
- Folder sizing: Avoids traversing linked folders when calculating directory sizes.
- Indexing: Correctly reaches included folders nested below excluded parents, including multiple separate nested includes.
- Indexing: Prevents modified-first path ordering from corrupting a folder prefix and skipping part of a reindex pass.
- Index cleanup: Matches stored paths without case sensitivity and continues cleaning other drives when one stored path is missing.
- Favorites: Clicking the Explore star now adds the selected path immediately and refreshes the star state.
- Favorites: Add, find, and remove operations now tolerate paths stored with or without a trailing backslash.
- Search Home: Hides path-favorite controls that do not apply to Home search-history actions.
- MoContext: Adds structured saved-context sections for major work, decisions and rationale, findings, and pending work.
- MoContext: Generates a readable weekly summary from recent activity and saved context.
- MoContext: Adds a configurable quality check that guides clients when a saved context summary is too thin.
- MoContext: Simplifies the local AI interface to 15 clearer tools while preserving compatibility with existing REST clients.
- MoContext: Combines search, browse, and recent-file discovery into a clearer find_files workflow.
- MoContext: Combines whole-file, line-range, and focused-window reading into a clearer read_file workflow.
- MoContext: Reports when indexed files may have changed since their last index update.
- MoContext: Adds an overall newest-index timestamp so clients can quickly judge search freshness.
- MoContext: Keeps activity from unsessioned clients grouped predictably, with optional client-specific grouping.
- MoContext: Truncates overlong activity text with a clear warning instead of rejecting the entire entry.
- MoContext: Refreshes weekly summaries promptly after later saves without losing background update signals.
- MoContext: Returns clear client errors for zero, negative, or reversed file-reading ranges.
- MoContext: Updates its MCP and SQLite components for improved long-running reliability and current database support.
- SQLite: Updates the bundled SQLite engine and command-line tools to 3.53.3.

## 9.50.7 — 2026, Jun 20

_Smoother updates, stronger recovery, and MoContext polish_

- Updates: Added quiet background downloads and an Apply Update button when installation is ready.
- Updates: Improved recovery from interrupted or failed downloads, with retry tracking and a manual-download fallback.
- Updates: Automatically cleans up obsolete cached installers without risking the installer currently in use.
- AutoIndexer: Fixed cases where indexing could fail to resume after file deletions or folder-monitor errors.
- AutoIndexer: Improved recovery after initial indexing so remaining database setup completes before AutoIndexer resumes.
- Reindex: Prevents automatic restart after canceled or incomplete reindexing.
- Diagnostics: Corrected memory reporting so peak usage is shown accurately.
- MoContext: Added project-folder scoping to search, browse, and evidence-pack retrieval over HTTP and MCP.
- MoContext: Scoped searches now report which project folder was searched, even when no results are found.
- MoContext: Improved search relevance so small path-only and media records no longer crowd out useful source files.
- MoContext: Redesigned the Status and Explore Context tabs for consistent light and dark themes.
- MoContext: Added normal keyboard navigation plus Alt+S and Alt+E shortcuts for switching tabs.
- MoContext: Added bottom spacing to Explore Context results for cleaner scrolling and presentation.
- MoContext: Updated its SQLite and MCP components to current releases.
- MoContext: Expanded diagnostics to report both managed and native SQLite versions.
- Search Home: Added a Search History heading and improved the layout of history rows and ranking controls.
- Search UI: Centralized search-box sizing and positioning across Home, Simple Search, Advanced Search, and Topbar modes.
- Search UI: Keeps Home history rows centered and 40 pixels narrower than the search box, with responsive narrow-window handling.
- Search UI: Double-clicking the minimized Topbar now restores its saved size and position.
- Search UI: Keeps the Configure button visible whenever the main Topbar is not minimized.
- Folder tree: Preserves empty and special folder selections when refreshing the tree.
- Icons: Refreshed MoSearch and MoContext Windows icons for stronger contrast and readability on dark taskbars.
- Documentation: Updated MoContext AI and human guidance for project-scoped retrieval.

## 9.50.6 — 2026, Jun 6

_Search Home, faster queries, MoContext memory, and indexing reliability_

- Search: Added a dedicated Search Home mode focused on fast searching, recent searches, often-used searches, and resuming prior work.
- Search: Added inline Search Home row actions such as deleting history entries directly from the Home view.
- Search UI: Polished Home and Simple Search layouts with a larger centered search box, shared layout behavior, a welcome state, and improved mode-button visibility.
- Search history: Added adaptive ranking that blends text match, recency, and frequency so suggestions better match how searches are actually reused.
- Search history: Added per-use timestamps and use counts while keeping older `SearchHistory.dat` files backward compatible.
- Search history: Refactored history launch behavior so saved filters restore through a common path, including switching back to Advanced mode when needed.
- QueryEngine v2: Added adaptive path-driven and path-prefilter plans for selective folder/path searches.
- QueryEngine v2: Added adaptive extension-driven and extension-prefilter plans for selective file-extension searches.
- QueryEngine v2: Improved reverse-wildcard and contains-wildcard filename searches with payload-late fetch and temp-table prefilter strategies.
- QueryEngine v2: Added word-first planning for multi-word and tag-word searches to reduce unnecessary Uri scans.
- QueryEngine v2: Added guardrails to avoid known-broad path or extension plans when those plans would be slower.
- Query diagnostics: Added clearer planner labels and SQLite scan-status/planner-stat output when diagnostics are enabled.
- Query testing: Added QueryEngine test profiles, compact summaries, JSONL progress sidecars, SQL-detail sidecars, and headless integrated profile runs.
- Database: Raised the MoSearch database version to 47 and added the 9.50.6 upgrade patch.
- Database: Added partial Uri tag indexes for `#NoData`, `#NoOpen`, `#TooBig`, high-ASCII, path-too-long, and encoding-related tag searches.
- Database: Refreshes SQLite statistics after reindex and avoids startup/shutdown `PRAGMA optimize` paths that can weaken STAT4 quality.
- Database: Prevents orphan fwc WordIDs during database maintenance.
- Indexing: Adds UriHistory records for non-initial indexing events, enabling better recent working-set signals for MoContext.
- AutoIndexer: Clarified overflow warning text, reduced unnecessary rewatching, and kept manual Reindex available for rare overflow cases.
- Path cache: Hardened path-cache invalidation around indexed-path changes.
- MoContext: Added long-term context digest save/load/search support backed by human-readable weekly Markdown files.
- MoContext: Added MCP/API tools for `save_context_digest`, `load_context_digest`, and `get_context_digest`.
- MoContext: Added digest startup validation, duplicate-id detection, retention archiving, load budgets, and support-report summaries.
- MoContext: Added UriHistory-based working-set hints so AI clients can see recently active files without loading file contents.
- MoContext: Added compact status UI improvements plus a tabbed Explore Context panel for inspecting LoadContext-style evidence packs.
- MoContext: Expanded support reports with context digest, MCP tool-call, dashboard, and transport diagnostics.
- MoContext: Expanded the API correctness harness for digest, working-set, API, and MCP coverage.
- SQLite: Updated bundled SQLite tooling and the amalgamation header area to SQLite 3.53.2, with scan-status support available for diagnostics.
- Installer: Version bumped to 9.50.6.0 across MoSearch, MoContext, installer scripts, patch scripts, and update-feed files.
- Installer: Final update-feed files point to `Install_Mo-Search_9.50.6.exe` with the Jun 6, 2026 release date.
- Documentation: Refreshed MoContext AI/human docs, `llms.txt`, local AI guidance, and release workflow notes for 9.50.6.

## 9.50.5 — 2026, Apr 26

_MoContext indexed memory, MCP discovery, installer hardening, and FileViewer cleanup_

- MoContext: Added MCP resources/templates and concise front-door calls including server summary, diagnostics, usage guide, context paths, context-file listing/reading, and memory-file writing.
- MoContext: Added per-user AppData context folders with product-owned `sys` docs and user/AI-owned `memory` notes for searchable long-term context.
- MoContext: Installed AI usage docs, human prompt guidance, and the consolidated human guide into both Program Files and the indexed AppData MoContext docs folder.
- MoContext: Split compact health from verbose diagnostics and refreshed dashboard/support-report data for the new diagnostics shape.
- MoContext: Added scoped context-file APIs with safe relative paths, extension limits, max-size checks, and read truncation.
- MoContext: Expanded the installed API smoke test to cover diagnostics, context paths/files, context-file reads, and MCP resource listing/reading.
- MoSearch indexing: Added the AppData MoContext folder to default indexed paths.
- MoSearch indexing: During install-mode customized-path loading, appends the AppData MoContext folder to existing custom path files without duplicating it.
- Installer: Version bumped to 9.50.5 across application, installer, patch installer, and update-feed files.
- Installer: Build/sign script now requires exactly one installer output and one patch output before signing or updating version files.
- Installer: Build/sign script now signs EXEs and DLLs before packaging and fixed the final completion/pause message flow.
- Installer: AppData MoContext `sys` docs are removed/replaced cleanly on upgrade while user-owned memory data is preserved on uninstall.
- FileViewer: Extracted media player, image, EXIF metadata, find, tab, status/footer, and command/action behavior into focused helper classes.
- FileViewer: Public handlers and message-map entry points now delegate to the helper panes while preserving existing UI behavior.
- Results context menu: Fixed shell command ID collisions by reserving separate ranges for Windows shell verbs and Mo-Search commands.
- Results context menu: Extracted selected-file shell menu workflow and centralized command ID translation.
- Search UI: Centralized filter combo maintenance, autocomplete close handling, topbar layout behavior, and drop-height refresh logic.
- Search UI: Polished recent-search dialog title/selection behavior.
- Find Duplicate Files: Fixed a 150% DPI saved-window-size issue that could reopen the tool too small.
- Website/docs: Refreshed MoContext public AI usage text, human guide links, `llms.txt`, sitemap, and release workflow notes for 9.50.5.

## 9.50.4 — 2026, Apr 12

_MoContext tools, diagnostics exports, and simple-search polish_

- MoSearch UI: Simple search combo now taller and uses simple-mode font sizing where applicable.
- MoSearch UI: Header tooltips simplified; simple mode hides report/sort/explore/go buttons.
- MoSearch UI: Inline simple-search magnifier button hidden in favor of cleaner layout.
- MoSearch UI: Search combo repaint reliability improved (cue text + redraw on set/selection changes).
- MoSearch UI: Other small simplifications for Simple mode.
- Application/code signing cert.
- FileViewer: Email compose now uses Simple MAPI with a mailto: fallback and clearer error messaging.
- MoContext: Added MCP tool surface (search, browse, evidence-pack, file-window/full-file, activity/session tools) with event tracking.
- MoContext: HTTP server bootstrap includes MCP transport, OAuth discovery response, and richer transport logging/diagnostics.
- MoContext: Evidence-pack retrieval now runs end-to-end against MoSl.db with ranking, windowing, budgets, and loader gating.
- MoContext: Repository now persists sessions, activity logs, saved packs, and event telemetry.
- MoContext: Support report export bundles health snapshot, dashboard model, and recent transport issue summaries.
- SQLite: Updated to 3.53 (compile-time options retained in top-level config section).

## 9.50.2 — 2026, Mar 15

_Search history, query engine tuning, and reliability fixes_

- Search: New Search History — stores up to 50 recent searches with full filter criteria; accessible from the clock-icon button in the filter bar. Supports favorites, keyword filter, delete, and re-run.
- Search: Query engine v2 — double-wildcard filename patterns (for example *config*) now use a temp-table pre-filter to build a small FileID set and avoid broader scans on large corpora.
- Search: Query engine v2 — word+path+ext queries now more consistently use the faster ext-driven path instead of falling back to broader scans.
- Search: Improved diagnostics — added planner labels (for example Plan=P4Temp / ExtDriven / PathDriven / FwcDriven), SQL metadata, statement-efficiency metrics, and scan summary details.
- Search: NOT-word queries (for example -error) now rank correctly; a previous NULL score path could suppress valid results.
- Search History: 'Last Used' timestamps now use 24-hour format, so sort order and auto-pruning behave correctly around midnight.
- Search History: Load logic now bounds-checks enum-like stored values, preventing bad filter state from corrupt or hand-edited SearchHistory.dat files.
- File types: RTF indexer reliability fix — extracted text length is now reported correctly even when content comes from Unicode or hex escape paths.
- Bug fix: 'Modified After' in search filters now defaults to midnight yesterday instead of 24 hours ago, preventing same-day misses.
- Bug fix: 'At Path, Launch... > File Analyzer' now opens the correct tool.
- Bug fix: Duplicate Files tool now applies the higher stdio handle ceiling in Release builds too, preventing failures on very large scans.
- Bug fix: Multithreading initialization issue resolved during startup.
- Bug fix: AutoIndexer reliability improvements.
- Reliability: Expanded automated and integrated test coverage across file-system, indexing, path, PDF, AVL tree, string allocation, and query-engine scenarios.
- AI: MoContext local HTTP server provides ranked source-code retrieval and activity journaling for AI agents (replaces earlier script-based interface).
- SQLite: SQLITE_ENABLE_STMT_SCANSTATUS is now available in all builds; runtime collection remains gated by diagnostics, so normal queries do not pay extra overhead.
- SQLite: Updated to 3.52.0.
- Visual Studio: Build environment updated to 18.4.0.

## 9.50.1 — 2026, Feb 18

_Rebuilt search engine, 30+ new file types, Python AI interface_

- Search: Rebuilt query engine v2 — modular compiler, planner, and execution engine replace the monolithic v1.
- Search: Smarter SQLite query planning with CROSS JOIN and index hints for faster, more selective queries.
- Search: Reverse-index filename searches — queries like `*er.h` now use a selective reverse index instead of a full table scan.
- Search: Extension narrowing from filename patterns (e.g. `*er.h` → `.h` files only), reducing search space automatically.
- Search: Double-wildcard patterns (`*test*`, `*config*`) correctly bypass the reverse-GLOB optimization.
- Search: New QueryEngineTester with 72 automated test cases covering both v1 and v2 engines for correctness and regression prevention.
- Indexer: Changed word partition algorithm to FNV-1a (997-way, replacing 961-way base-31) for better distribution and faster querying on large corpora.
- Indexer: Increased default .md max indexing size from 1 KB to 8 KB.
- Indexer: Fixed long-standing issues where some files re-indexed needlessly slow, with incorrect counts and metadata.
- Indexer: New MosPerf timing infrastructure for profiling indexer and query paths.
- File types: Native RTF indexer — indexes .rtf files up to 16 MB without iFilter dependency.
- File types: 7z archive indexer — indexes filenames contained within .7z archives (LZMA SDK).
- File types: New PDFium integration for native PDF text extraction, replacing old zlib-based extractor (removed zlib dependency).
- File types: 30+ new extensions indexed by default: .py, .rb, .go, .rs, .swift, .kt, .scala, .lua, .dart, .groovy, .cfg, .yaml, .toml, .env, .tf, .gradle, .cmake, .proto, .graphql, .rst, .gitignore, .ods, .xlsx, .pptx, .epub, .svg, .fsproj, .war, .ear.
- AI: MoContext HTTP API for AI agents — evidence-pack retrieval, file reading, and activity journaling on http://127.0.0.1:43210 (replaces earlier PowerShell/Python script interface).
- Installer: Minimum OS is now Windows 10 or later (Windows 7/8 support dropped; removed UCRT shim DLLs).
- Installer: Updated to Visual Studio 2026 v145 toolset and Windows SDK 10.0.26100.0.
- UX: Various UI fixes and improvements.

## Earlier releases

| Version | Date | Release |
|---|---|---|
| 9.49.24 | 2026, Jan 19 | 44 changes |
| 9.49.13 | 2025, Dec 31 | 49 changes |
| 9.49.10 | 2025, Nov 11 | 7 changes |
| 9.49.9 | 2025, Oct 20 | 2 changes |
| 9.49.8 | 2025, Oct 19 | 9 changes |
| 9.49.7 | 2025, Oct 13 | 22 changes |
| 9.49.6 | 2025, Aug 23 | 5 changes |
| 9.49.5 | 2025, July 27 | 28 changes |
| 9.49.4 | 2025, June 8 | 5 changes |
| 9.49.3 | 2025, June 2 | 15 changes |
| 9.49.2 | 2025, May 6 | 0 changes |
| 9.49.1 | 2025, May 5 | 7 changes |
| 9.49.0 | 2025, Mar 25 | 0 changes |
| 4.0.16 | 2012, Apr 27 | 14 changes |
| 4.0.15 | 2012, Mar 27 | 24 changes |
| 4.0.14 | 2012, Jan 19 | 10 changes |
| 4.0.13 | 2012, Jan 3 | 3 changes |
| 4.0.12 | 2011, Dec 21 | 12 changes |
| 4.0.11 | 2011, Nov 9 | 6 changes |
| 4.0.10 | 2011, Oct 31 | 9 changes |
| 4.0.9 | 2011, Oct 22 | 4 changes |
| 4.0.8 | 2011, Oct 06 | 9 changes |
| 4.0.7 | 2011, Sep 27 | 6 changes |
| 4.0.6 | 2011, Sep 19 | 14 changes |
| 4.0.5 | 2011, Jul 03 | 3 changes |
| 4.0.4 | 2011, Jun 27 | 2 changes |
| 4.0.3 | 2011, Jun 21 | 6 changes |
| 4.0.2 | 2011, Jun 17 | 4 changes |
| 4.0.1 | 2011, Jun 08 | 4 changes |
| 4.0.0 | 2011, May 25 | 4 changes |
| 3.1.1 | 2010, Nov 2 | 25 changes |
| 3.1.0 | 2009, Jan 05 | 72 changes |
| 3.0.0 | 2007, Dec 31 | 31 changes |
| 2.7.1 | 2007, Sept 22 | 24 changes |
| 2.7 | 2007, Jun 7 | 52 changes |
| 2.5.6 | 2006, Dec 24 | 27 changes |
| 2.5.5 | 2006, Nov 18 | 26 changes |
| 2.5.4 | 2006, Sep 16 | 22 changes |
| 2.5.3 | 2006, Jul 08 | 20 changes |
| 2.5.2 | 2006, May 6 | 27 changes |
| 2.5.1 | 2006, Mar 26 | 15 changes |
| 2.5 | 2006, Mar 19 | 29 changes |
| 2.3.1 | 2005, Nov 07 | 8 changes |
| 2.3 | 2005, Oct 14 | 15 changes |
| 2.2.8 | 2005, Sept 16 | 6 changes |
| 2.2.7 | 2005, Sept 14 | 6 changes |
| 2.2.6 | 2005, Aug 30 | 25 changes |
| 2.2.5.1 | 2005, Aug 13 | 2 changes |
| 2.2.5 | 2005, Aug 13 | 17 changes |
| 2.2.4 | 2005, Aug 11 | 25 changes |
| 2.2.3 | 2005, Aug 08 | 15 changes |
| 2.2.2 | 2005, Jun 29 | 7 changes |
| 2.2.0 | 2005, May 19 | 7 changes |
| 2.1.3 | 2005, May 04 | 13 changes |
| 2.0.2 | 2005, Apr 14 | 13 changes |
| 1.9.9 | 2005, Feb 21 | 4 changes |
| 1.9.8 | 2005, Feb 10 | 1 change |

---

Full release notes for every version are published at [meauxsoft.com](https://www.meauxsoft.com/MoSearch_Releases.html).
