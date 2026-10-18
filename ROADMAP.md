# Forma Roadmap

Forma Alpha 1 is version `0.1.1-alpha.1`. This roadmap separates features included in the release from ideas discussed for later development. Planned and exploratory items have no promised dates.

## Included in Alpha 1

Forma is a local-first desktop application. Its Alpha 1 feature set includes:

- **Markdown Notes** stored as Markdown files, with a protected read-only fallback when content cannot be safely round-tripped through the rich-text editor.
- **Structured Pages** with rich-text content, properties, icons, covers and reusable sections.
- **Database V2** with Table, Board, Gallery and List views, backed by local files and a journal.
- **Tabs and split views** for working with multiple documents.
- **Attachments and images**, including local previews.
- **Built-in Markdown templates**, including Client Discovery Meeting and Creative Brief.
- **Local workspace storage**, with workspace selection and persisted application preferences.
- **Recovery and backups**, including recovery snapshots, conflict handling, database journalling and ZIP export.
- **Application updates**, with an optional updater and signed updater packages.

Automated tests cover parts of these features; passing tests do not establish that every feature has been verified through the desktop interface. See [Known Issues](KNOWN_ISSUES.md) for test results and limitations.

## Planned

The following improvements have been discussed for future versions. They are not release commitments and have no confirmed dates:

- More image controls and editing.
- More editable tables and advanced content blocks.
- Broader Markdown compatibility.
- Richer layouts for Structured Pages.
- Further improvements to inline databases in Pages.
- Better drag-and-drop organisation.
- Improved search and workspace navigation.
- Incremental consistency improvements to navigation, dropdowns and block menus.

## Deferred

A complete redesign of navigation, dropdowns and block menus is deferred. Smaller consistency improvements may be considered as part of incremental interface work.

## Exploring

These are longer-term ideas for research; there is no commitment to build them:

- Visual Canvas documents for arranging and connecting material freely.
- Optional synchronisation between devices.
- Possible mobile support.

## Feedback

Please [report a bug or request a feature](https://github.com/Alitom297/Forma-Releases/issues).
