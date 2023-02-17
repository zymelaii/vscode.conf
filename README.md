# vscode.conf

### Target Version
> `VSCodeSetup-x64-1.68.1.exe (windows)` <br>

### Initial Setup
Download an appropriate version of VSCode and setup for yourself. <br>
PS: replace official download server `az764295.vo.msecnd.net` (or anything else appeared in your download link) to `vscode.cdn.azure.cn` to speed up your download procedure. `[optional]`

### Recommended Extensions Installation (independent extension plugins can be remove)
1. `Chinese (Simplified) (简体中文) Language Pack for Visual Studio Code` <br>
    **brief** Language pack extension for Chinese (Simplified)
2. `Error Lens` <br>
    **brief** Improve highlighting of errors, warnings and other language diagnostics.
3. `Markdown All in One` <br>
    **brief** All you need to write Markdown (keyboard shortcuts, table of contents, auto preview)
4. `clangd` <br>
    **brief** C/C++ completion, navigation and insights based on clangd (LSP project of LLVM)
5. `CMake Tools` <br>
    **brief** CMake language with extension support
6. `Bookmarks` <br>
    **brief** Mark lines and jump to them
7. `Pylance` <br>
    **brief** A performant, feature-rich language server for Python in VS Code
8. `Project Manager` <br>
    **brief** Easily switch between projects
9. `PlantUML` <br>
    **brief** Rich PlantUML support
10. `Todo Tree` <br>
    **brief** Show TODO, FIXME, etc. comment tags in a tree view

### Git Configure
1. Install `Git` for yourself.
2. Add `Git` to system PATH or turn to 3.
3. Mannually set `Git: Path` to the abosulte path of your Git in VSCode.

### Language Server Protocol Configure
Take many factors into consideration, my solution to LSP server is to install and configure clangd of LLVM project for VSCode.

1. Download latest LLVM released binaries from [official site](https://releases.llvm.org/) or manually build the projects from source code, install them to a propriate folder (marked as `$LLVM_ROOT`) afterwards.
2. Install `clangd` extension for vscode.
3. Open settings of extension `clangd`, set `Clangd: Path` to `$LLVM_ROOT\bin\clangd.exe` (type absolute path of clangd.exe here).
4. Modify `settings.json` of VSCode, append content as [`clangd.cfg`](./config/clangd/clangd.cfg).
5. Create `.clangd` file at the root path of workspace or at, edit as [`.clangd`](./config/clangd/.clangd) or whatever you want, for more information, browser [official site of clangd](https://clangd.llvm.org).
6. For global configuration, edit and put the config file [`clangd/config.yaml`](./config/clangd/config.yaml) into the user directory (defaultly `%USERPROFILE%/AppData/Local` on Windows) according to the help information provided by `clangd`. In addition, relevant config files `.clang-tidy`/`.clang-format` for `clang-tidy`/`clang-format` can be put into the root path of any workspace to implement global configuration.

### Snippet Configure
- [C](./config/snippet/c.json)
- [C++](./config/snippet/cpp.json)
- [CMake](./config/snippet/cmake.json)

### Keybinding Configure
#### `Rebinded Commands`
- ★★★★★ `editor.action.blockComment` `"ctrl+shift+/"`
- ★★★★★ `editor.action.insertCursorAtEndOfEachLineSelected` `"ctrl+shift+l"`
- ★★★★★ `editor.action.selectHighlights` `"shift+alt+d"`
- ★★★★★ `breadcrumbs.focusAndSelect` `"ctrl+shift+."`
- ★★★★★ `editor.action.moveLinesUpAction` `"ctrl+shift+up"`
- ★★★★★ `editor.action.moveLinesDownAction` `"ctrl+shift+down"`
- ★★★★☆ `editor.action.quickFix` `"ctrl+shift+."`
- ★★★★☆ `editor.action.jumpToBracket` `"ctrl+m"`
- ★★★★☆ `editor.action.transformToUppercase` `"ctrl+k ctrl+u"`
- ★★★★☆ `editor.action.transformToLowercase` `"ctrl+k ctrl+l"`
- ★★★★☆ `workbench.action.toggleSidebarVisibility` `"ctrl+alt+b"`
- ★★★☆☆ `selectAllSearchEditorMatches` `"shift+alt+d"`
- ★★★☆☆ `addCursorsAtSearchResults` `"shift+alt+d"`
#### `Removed Commands`
- notebook.cell.detectLanguage
- editor.action.formatSelection
- editor.detectLanguage
- editor.action.toggleTabFocusMode
- editor.toggleFold
- editor.action.removeCommentLine
- editor.action.inPlaceReplace.up
- workbench.action.files.saveWithoutFormatting
- editor.action.copyLinesUpAction
- editor.action.copyLinesDownAction
- editor.action.insertCursorAbove
- editor.action.insertCursorBelow
- editor.action.autoFix
- clangd.typeHierarchy
- breadcrumbs.toggleToOn
- cursorColumnSelectDown
- cursorColumnSelectLeft
- cursorColumnSelectPageDown
- cursorColumnSelectPageUp
- cursorColumnSelectRight
- cursorColumnSelectUp
- problems.action.showQuickFixes
- workbench.action.openSettings
#### `Recommended Commands (except for cmds above)`
- `editor.action.triggerSuggest` `"ctrl+i"`
- `editor.action.addSelectionToNextFindMatch` `"ctrl+d"`
- `editor.action.trimTrailingWhitespace` `"ctrl+k ctrl+x"`
- `editor.action.insertLineAfter` `"ctrl+enter"`
- `editor.action.insertLineBefore` `ctrl+shift+enter`
- `editor.action.formatDocument` `"shift+alt+f"`
- `clangd: Switch Between Source/Header` `"alt+o"`
- `workbench.action.editor.changeLanguageMode` `"ctrl+k m"`
- `workbench.action.togglePanel` `"ctrl+j"`
- `workbench.action.terminal.toggleTerminal` `"ctrl+backtick"`
- `workbench.action.terminal.new` `"ctrl+shift+backtick"`
- `workbench.action.closeFolder` `"ctrl+k f"`
- `editor.action.refactor` `"ctrl+shift+r"`
- `workbench.action.quickOpen` `"ctrl+p"`
- `workbench.action.showCommands` `"ctrl+shift+p"`
- `workbench.action.gotoLine` `"ctrl+g"`
- `workbench.action.openRecent` `"ctrl+r"`
- `markdown.showPreviewToSide` `"ctrl+k v"`
