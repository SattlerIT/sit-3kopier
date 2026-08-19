# Changelog — S-IT-3Copy

All notable changes to S-IT-3Copy, newest first.

## v3.3.2.9 — August 2026 · International edition

- **New:** The tool speaks four languages – German, English, French and Spanish. The language is chosen during installation and can be changed at any time under ⚙; the selection shows the matching flag for each language. The program name changes with it: 3Kopier, 3Copy, 3Copier, 3Copiar.
- Translated are the interface, all dialogs, the messages shown while copying, the scheduler and the logs. Each language has its own help page; the pages link to one another.
- File names and settings stay the same in every language (`3Kopier.ini`, profiles as `.3ko`, folder `Logs`) – switching language changes nothing about existing profiles, filters and settings.
- **Improved:** Settings (⚙) are now laid out in two columns – language and scaling on the left, log retention and log detail on the right. This makes the window considerably shorter, so it fits on screen even at high scaling.
- **Improved:** The buttons in the profile bar size themselves to the length of their labels, so the text has enough margin in every language.

## v3.3.2.8 — August 2026

- **New:** Timestamp tolerance against drift on NAS and network drives – in "only if newer" mode, unchanged files are no longer mistaken for newer ones because of second-level timestamp differences and copied again on every run (tolerance of 2 seconds, as with Robocopy /FFT).
- **New:** 🛡 symbol per profile (next to 🚫) – sets that tolerance (Automatic / Always / Off); "Automatic" only applies to `\\` network paths and is the default, "Always" helps with network drives mapped to a drive letter (`X:`, `Y:` …).
- **Improved:** Paths in the job overview are no longer cut off at the edge but shortened cleanly (beginning…end); the full path is shown in the tooltip.
- **Fixed:** The action window could not be minimised when started from the open scheduler window; the close button (X) now works like ⏹ Stop and cleanly aborts only that one run.

## v3.3.2 — July 2026

- **New:** Speed display – while copying, the status line shows the current transfer rate (e.g. `157.4 MB/s`), in the scheduler's progress window as well.
- **New:** Job filter (🔰) per job – additional exclusions for that job only, or an ONLY rule ("copy only certain file types"), e.g. job 1 only `*.pdf`. The 🔰 symbol turns green as soon as a rule is set; profile-wide exclusions still apply in addition.
- **New:** Selectable log detail (⚙) – Compact (default) with one summary line per job, Detailed with one line per folder; errors are always logged in full.
- **New:** Queue for the scheduler – colliding runs are no longer lost but run one after another; result windows do not block the next run, ⏹ Stop only aborts the current one. The action window also appears in tray mode and can be minimised; aborted runs are marked in the log as "FAZIT (ABGEBROCHEN)".

## v3.3.1 — July 2026 · Move to Python

- Complete move from AutoIt to Python – operation and workflow unchanged, existing `3Kopier.ini` and `.3ko` profile files keep working without any adjustment.
- Copy runs happen in the background – the interface stays responsive even with very many files or slow network drives; block-wise copying, "Stop" takes effect immediately.
- **New:** automatic scheduler – run profiles in the background on a schedule, including silent mode and tray operation with autostart.
- **New:** exclusion list – leave files and whole folders (browser caches, temporary files, large image formats) out of the copy; with sensible defaults, adjustable per profile.
- **New:** sleep mode after copying as an alternative to shutting down (the two options are mutually exclusive).
- New settings (⚙): scaling 90–200 %, log retention (1 day to unlimited) with immediate cleanup; logs are now a separate file per run in the `Logs` folder.
- Result window reworked (one column per job); the profile drop-down loads immediately without a "Load" button; very long paths are shown shortened (beginning…end), full path in the tooltip.
- Network/NAS paths (UNC) improved, data volume calculated without freezing; the result summary is now at the top; smaller layout corrections; `Lizenz.txt` is included.

## v3.2.1 — AutoIt version

- Automatic handling of long paths (MAX_PATH): target paths of 260 characters or more are shortened automatically – the file name first, the last subfolder as well if needed. Shortened names get the marker `-3k`.
- Data volume also counted correctly for long paths, in the display and in the progress bar.
- Log size automatically limited to 512 KB – the oldest entries are removed, current runs are kept.

## v3.2.0 — AutoIt version

- Overwrite/move options per job are now saved both in the INI file and in `.3ko` profiles.
- Target folders are created before the check; network paths are skipped when calculating the data volume, without freezing.
- Visual corrections: header spacing, label widths and checkbox positions reworked.

---

© 2026 Sattler IT-Service, Greifenstein · Author: Hans Udo Sattler
