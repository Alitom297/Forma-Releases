# Forma Alpha 1: Known Issues and Testing

Forma Alpha 1 is version `0.1.1-alpha.1`. This document distinguishes confirmed limitations from historical reports, fixed defects and areas that have not been verified.

## Confirmed limitations

- **Platform support:** Windows is experimental. Its build artefacts and updater signatures have been inspected, but the application has not been natively tested on Windows.
- **macOS installation warnings:** The macOS DMG is not notarised and may trigger a Gatekeeper warning. Windows users may see a SmartScreen warning because the installer is unsigned.
- **Markdown compatibility:** Markdown content that cannot be safely round-tripped through the rich-text editor opens in a read-only safety fallback. Broader Markdown compatibility remains future work.
- **Backups:** Forma supports ZIP export. An automatic backup schedule and a complete in-app restore workflow are not established for Alpha 1.
- **Filesystem changes:** Moving or renaming workspace files outside Forma may leave references out of date. Files moved through the operating system are not automatically reconciled.
- **Database durability:** Database V2 uses a journal for recovery, but that does not establish transactional guarantees across every related file or filesystem operation.
- **Image references:** Local image references may need attention after moving notes or folders. The exact conditions should be confirmed when reproducing a report.

## Historical reports requiring reproduction

- **Markdown template fallback:** Client Discovery Meeting and Creative Brief templates were reported to open intermittently in the read-only Markdown fallback. Automated tests passed, but the intermittent native report was not confirmed as resolved.
- **Moved image references:** Image previews were reported to fail in some cases after moving notes or folders. The precise reproduction conditions remain unclear.

These reports should be reproduced before being described as confirmed current defects.

## Fixed defects

- **Recovery discovery and directory entries:** Recovery discovery previously could fail when it encountered a directory where it expected a file, preventing valid Markdown recovery snapshots from being offered. The handling was fixed and regression-tested.
- **Recovery write ordering:** A delayed recovery write could recreate a snapshot after retirement. Per-document write serialisation was added and covered by deterministic automated tests.

## Untested or partially tested

- **Native recovery:** In the isolated macOS recovery matrix, 7 of 12 cases passed. The remaining cases were blocked or unverified; they must not be treated as passes.
- **Windows:** No native Windows verification has been completed, including recovery, installation, updates or normal application use.
- **Application identity upgrade:** Migration from `com.forma.notes` to `com.forma.app` is implemented with copy-first handling, retains original data and avoids overwriting destination files without conflict handling. Automated migration tests passed. A native upgrade from an existing installation has not been tested on macOS or Windows.
- **Updater:** Signed updater artefacts and signatures were inspected, but a complete update from a published feed through download, verification, installation and restart has not been verified end to end.
- **Desktop interaction:** Automated tests cover selected behaviours. They do not verify every control, document type or workflow through the native application.

## Automated test evidence

The recorded local verification included:

- 589 frontend tests passed.
- 54 Rust tests passed.
- 9 release-tooling tests passed.
- TypeScript checks and the production build passed.

These results cover automated checks only. They do not replace the native verification gaps listed above.

## Reporting an issue

Please [report a bug or request a feature](https://github.com/Alitom297/Forma-Releases/issues). Include your operating system and Forma version, and provide steps to reproduce the issue where possible.
