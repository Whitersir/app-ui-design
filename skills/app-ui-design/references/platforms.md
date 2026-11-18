# Platform patterns

Usability layer — run after the visual work, on the changed flow only. These checks prevent broken behavior; they do not replace the taste rules in SKILL.md.

## Web

- Verify at wide desktop, narrow laptop, and phone widths. Check the layout at the awkward middle sizes, not just the breakpoints. Use the webapp-testing skill to screenshot and interact with the running page.
- Check keyboard traversal, visible focus, and hover states that also work without hover. Verify text scaling to 200% and reduced-motion behavior for any animation.
- Confirm real content extremes: the longest label, an empty list, a slow-loading image. Check contrast of muted text against its actual background, not the token value in isolation.

## Desktop

- Inspect the normal window size and usable minimum. Use split panes, tables, sidebars, or toolbars where they help users scan and operate on real work. Define which pane grows, what can scroll, and where long labels truncate. Keep essential actions reachable in a resized window and at the display scales the project supports.
- Prefer familiar menus, dialogs, shortcuts, and selection patterns. Check tab order, keyboard activation, visible focus, and focus restoration after a dialog. Show useful context actions for a selection when the task warrants them. Keep frequent actions accessible without relying on hover or right-click alone.
- Match the app's window chrome, system appearance, and file dialogs. In Electron and Tauri, check the packaged window as well as the renderer when the work touches menus, shortcuts, window sizing, file handling, or other host integration.

## Mobile

- Use the project's platform-appropriate navigation and back behavior. Keep the primary action reachable with one hand where it matters. Make surrounding content scroll if needed and keep tappable controls clear of safe-area insets and system gestures.
- Use platform-appropriate touch target sizes and leave enough separation between neighboring actions. Give forms the right keyboard and input semantics. Check that the focused field, errors, and the next action remain reachable while the software keyboard is open.
- Check small and large supported screens, larger text, and any supported orientation. Verify back behavior, focus order, and recovery after interrupted input. For cross-platform apps, use common components where behavior is shared and adapt the places where platform conventions differ.

## Interactive terminal

- Design for terminal rows and columns. Give long values a predictable truncation or wrapping strategy and keep the focused item and key hints identifiable at supported sizes. Verify resizing and text widths with representative data, including wide characters if the app supports them.
- Make navigation, activation, and exit discoverable with concise key hints. Preserve expected keyboard behavior across lists, inputs, and modal screens. Convey status and selection with text or symbols as well as color.
- Try the normal terminal entry point with keyboard input, a narrow window, and the project's supported color modes. If changes affect terminal state, check that normal exit and cancellation restore the shell. Preserve plain output for existing scripts and pipes when the application also has a non-interactive mode.
