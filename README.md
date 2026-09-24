# Browser tab middle-click evidence

Captured on macOS with Electron 43.4.1, the real BrowserPanel component and DesktopBrowserManager, an isolated temporary user-data directory, and three localhost pages.

- before.png: original BrowserTabStrip at eaa61eded, after middle-clicking the background tab; all three tabs remain.
- after.png: BrowserTabStrip at be425b55a, after the same middle click; the background tab closes and the original active tab remains selected.
- interaction.mov: middle-click closes the background tab, then the active tab, then the last tab. The existing last-tab behavior opens a replacement blank tab.

The fixture checks the manager state and IPC call log, including one closeTab call per click and no selectTab calls. These are native window captures. This is focused macOS runtime evidence, not Windows/Linux or packaged-release validation.
