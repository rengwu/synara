# Browser address suggestions: native layering regression

Captured on macOS with Electron 43.4.1, the real `BrowserPanel` component, and the real `DesktopBrowserManager`, in an isolated fixture with a temporary user-data directory and a localhost page. These are native window captures, not DOM-only browser screenshots.

- `before.png`: original main behavior at eaa61eded; the native page covers the suggestion rows below its upper boundary.
- `after.png`: fix at 58be32550; suggestions remain visible while the native page is temporarily occluded.
- `restored.png`: dismissing the suggestions restores the same page.
- `interaction.mov`: opening suggestions, dismissing them, and selecting a navigation suggestion after the fix.

The fixture also checked that the same Electron webContents ID survived dismissal and navigation. This is focused macOS runtime evidence, not a packaged release test or a Windows/Linux validation.
