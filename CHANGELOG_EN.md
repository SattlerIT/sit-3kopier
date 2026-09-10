# Changelog — S-IT-3Kopier

All notable changes to S-IT-3Kopier, newest first.

## v3.3.2.15 — September 2026 · Eighteen languages and a tidy program directory

- **New:** Twelve more languages – **Croatian, Slovenian, Serbian, Bosnian, Montenegrin, Bulgarian, Macedonian, Albanian, Romanian, Turkish, Polish, and Danish**. The tool now speaks eighteen languages. The program name changes accordingly: 3Kopiraj, 3Copiază, 3Kopyala, 3Kopiuj.
- As usual, the interface, dialogs, messages, scheduler, and logs are translated; each language has its own help page.
- **New:** The program directory is now tidy. Language files, help pages, settings, and profiles now reside in their own folders (`Lang`, `Help`, `Config`, `Profile`); only the program and `_internal` remain at the root. Existing installations will reorganize themselves on first start – profiles, schedules, and settings are preserved and do not need to be touched.
- **New:** The setup also speaks eighteen languages. Its language files now sit next to the setup file instead of inside it, allowing additional languages to be added without a new program build.
- **Improved:** The language selection under ⚙ adjusts to the number of languages found – two, three, or four columns. The flags are left-aligned, providing a calm display even with eighteen entries.
- **Improved:** Help pages no longer link to each other. Instead, the help follows the language set under ⚙ – so no link points into the void if a package doesn't contain all languages.
- The feature set remains unchanged – existing profiles, filters, and settings are unaffected.

## v3.3.2.10 — September 2026 · Dutch and Italian

- **New:** Two more languages – **Dutch** and **Italian**. The tool now speaks six languages. The program name changes accordingly: 3Kopieer and 3Copia.
- As usual, the interface, dialogs, messages, scheduler, and logs are translated; both languages have their own help page.
- The language bar on all help pages now lists six languages.
- The program itself remains unchanged – existing profiles, filters, and settings are unaffected.

## v3.3.2.9 — August 2026 · International version

- **New:** The tool now speaks four languages – German, English, French, and Spanish. The language is selected during installation and can be changed at any time under ⚙; the selection shows the corresponding flag for each language. The program name changes accordingly: 3Kopier, 3Copy, 3Copier, 3Copiar.
- The interface, all dialogs, copy messages, scheduler, and logs are translated. Each language has its own help page; pages are linked to each other.
- File names and settings remain the same across all languages (`3Kopier.ini`, profiles as `.3ko`, folder `Logs`) – changing languages does not affect existing profiles, filters, or settings.
- **Improved:** Settings (⚙) are now displayed in two columns – left for language and scaling, right for log retention and detail. The window is significantly shorter and fits entirely on screen even at high scaling.
- **Improved:** The profile bar buttons adapt to the length of their label, ensuring enough margin for the text in each language.

## v3.3.2.8 — August 2026

- **New:** Timestamp tolerance against drift on NAS and network drives – in "only if newer" mode, unchanged files are no longer mistakenly recognized as newer due to timestamp second deviations and re-copied on every run (tolerance of 2 seconds, like Robocopy /FFT).
- **New:** 🛡 icon per profile (next to 🚫) – sets this tolerance (Automatic / Always / Off); "Automatic" only affects `\\` network paths and is the default, "Always" helps with mapped network drives (`X:`, `Y:` …).
- **Improved:** Paths in the job overview are no longer cut off at the edge, but displayed cleanly truncated (beginning…end); the full path is shown in the tooltip.
- **Fixed:** The action window could not be minimized on launch from the open scheduler window; the close (X) button now behaves like ⏹ Stop and only aborts that one run cleanly.

## v3.3.2 — July 2026

- **New:** Speed display – the status bar shows the current transfer rate during copying (e.g., `157.4 MB/s`), also in the scheduler's progress window.
- **New:** Job filters (🔰) per job – additional exclusions only for that job or an ONLY rule ("copy only certain file types"), e.g., Job 1 only `*.pdf`. The 🔰 icon turns green once a rule is set; profile-wide exclusions still apply additionally.
- **New:** Log detail selectable (⚙) – Compact (default) with one summary line per job, Verbose with one line per directory; errors are always listed fully in the log.
- **New:** Queue for the scheduler – colliding runs are no longer lost but run sequentially; result windows do not block the next run, ⏹ Stop only cancels the current run. The action window also appears in tray mode and can be minimized; cancellations are logged as "RESULT (CANCELLED)".

## v3.3.1 — July 2026 · Switch to Python

- Complete switch from AutoIt to Python – operation and workflow unchanged, existing `3Kopier.ini` and `.3ko` profile files work without adjustment.
- Copy operations run in the background – the interface remains responsive even with many files or slow network drives; block-wise copying, "Stop" takes effect immediately.
- **New:** Automatic scheduler – execute profiles on a schedule in the background, including silent mode and tray mode with autostart.
- **New:** Exclusion list – exclude files and whole folders (browser caches, temporary files, large image formats) from copying; includes defaults out-of-the-box, adjustable per profile.
- **New:** Sleep mode after copying as an alternative to shutdown (both options are mutually exclusive).
- New settings (⚙): Scaling 90–200 %, log retention (1 day to unlimited) with immediate cleanup; logs now as separate file per run in the `Logs` folder.
- Result window revised (separate column per job); profile dropdown loads immediately without a "Load" button; very long paths are displayed truncated (beginning…end), full path in tooltip.
- Network/NAS paths (UNC) improved, data size calculation without freezing; result summary now at the top; minor layout corrections; `Lizenz.txt` included.

## v3.2.1 — AutoIt version

- Automatic handling of long paths (MAX_PATH): target paths over 260 characters are automatically shortened – first the file name, then the last subfolder if needed. Shortened names get the `-3k` marker.
- Data size correctly reflected in display and progress bar even with long paths.
- Log size automatically limited to 512 KB – oldest entries are removed, current runs are preserved.

## v3.2.0 — AutoIt version

- Overwrite/Move options per job are now saved both in the INI and in `.3ko` profiles.
- Target directories are created before verification; network paths are skipped during data size calculation without freezing.
- Visual corrections: header spacing, label widths, and checkbox positions revised.

---

© 2026 Sattler IT-Service, Greifenstein · Author: Hans Udo Sattler