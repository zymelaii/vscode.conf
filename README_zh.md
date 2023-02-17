# 我的 VSCode 配置历程

### 配置的 VSCode 目标版本
> `VSCodeSetup-x64-1.68.1.exe (windows)` <br>

### 安装 VSCode
从 VSCode 官网下载一个合适的版本并按步骤安装。 <br>
PS: 国内用户如果下载速度太慢，可以将下载链接中的域名段（如`az764295.vo.msecnd.net`）替换为`vscode.cdn.azure.cn`（国内云服务器）来加速下载。

### 推荐安装的插件（安装时附带的拓展包若非依赖项皆可卸载）
1. `Chinese (Simplified) (简体中文) Language Pack for Visual Studio Code` <br>
    **简介** VSCode 简体中文语言拓展包
2. `Error Lens` <br>
    **简介** 更好的程序诊断高亮
3. `Markdown All in One` <br>
    **简介** Markdown 集成拓展包（支持热键、表格、自动预览等）
4. `clangd` <br>
    **简介** LLVM 用于 C/C++ 的 LSP 服务器 —— clangd 的 VSCode 支持插件
5. `CMake Tools` <br>
    **简介** CMake 支持及其拓展
6. `Bookmarks` <br>
    **简介** 书签标记及跳转支持
7. `Pylance` <br>
    **简介** 用于 Python 的 LSP 服务器 Pylance 的 VSCode 支持插件
8. `Project Manager` <br>
    **简介** 项目管理器，能够更方便地在保存过的项目和 Git 仓库间切换
9. `PlantUML` <br>
    **简介** PlantUML 支持
10. `Todo Tree` <br>
    **简介** 树形结构罗列出工作区中的 TODO 、FIXME 等注释标签

### Git 配置
1. 安装 Git 。
2. 将 Git 添加到系统环境变量，或者按照步骤3操作。
3. 手动将已经安装的 Git 的绝对路径写入 VSCode 的`Git: Path`（可以直接在 settings.json 中添加或修改`git.path`属性）。

### C/C++ 的 LSP 配置
考虑多方面因素，我采用了 LLVM 的 clangd 来配置 VSCode 的 LSP 层。

1. 从 LLVM 的[官网](https://releases.llvm.org/)下载最新版的二进制发行文件或手动从项目源码编译，完成后将其安装到一个合适的目录中（此处记为 `$LLVM_ROOT`）。
2. 为VSCode安装`clangd`拓展插件。
3. 在拓展插件`clangd`的配置中设置`Clangd: Path`为`$LLVM_ROOT\bin\clangd.exe`（即安装的 clangd 可执行文件的绝对路径）。
4. 编辑 VSCode 的`settings.json`文件，参照[`clangd.cfg`](./config/clangd/clangd.cfg)附加相关内容（必要时可去除所给内容中的注释）。
5. 在工作环境根目录创建[`.clangd`](./config/clangd/.clangd)并依参照编辑（或自行调整）以细化`clangd`的配置（访问[官网](https://clangd.llvm.org)以获取更多信息）。
6. 若需要在全局配置`clangd`，依据`clangd`帮助信息的指导在用户目录（ Windows 平台下为`%USERPROFILE%/AppData/Local`）编辑[`clangd/config.yaml`](./config/clangd/config.yaml)作为`clangd`的配置信息。其中`clangd`将在当前工作目录及工作目录的任意级别父目录搜索`clang-tidy`/`clang-format`的配置文件`.clang-tidy`/`.clang-format`的配置文件，若需要为其添加全局配置，可尝试在工作目录的父级根目录编辑添加配置文件。

### Snippet 配置（个人偏好）
- [C 片段](./config/snippet/c.json)
- [C++ 片段](./config/snippet/cpp.json)
- [CMake 片段](./config/snippet/cmake.json)

### 快捷键绑定（个人偏好）
#### `重新绑定的命令`
- ★★★★★ `切换块注释` `"ctrl+shift+/"` `editor.action.blockComment`
- ★★★★★ `在行尾添加光标` `"ctrl+shift+l"` `editor.action.insertCursorAtEndOfEachLineSelected`
- ★★★★★ `选择所有找到的查找匹配项` `"shift+alt+d"` `editor.action.selectHighlights`
- ★★★★★ `breadcrumbs.focusAndSelect` `"ctrl+shift+."` `breadcrumbs.focusAndSelect`
- ★★★★★ `向上移动行` `"ctrl+shift+up"` `editor.action.moveLinesUpAction`
- ★★★★★ `向下移动行` `"ctrl+shift+down"` `editor.action.moveLinesDownAction`
- ★★★★☆ `快速修复` `"ctrl+shift+."` `editor.action.quickFix`
- ★★★★☆ `转到括号` `"ctrl+m"` `editor.action.jumpToBracket`
- ★★★★☆ `转换为大写` `"ctrl+k ctrl+u"` `editor.action.transformToUppercase`
- ★★★★☆ `转换为小写` `"ctrl+k ctrl+l"` `editor.action.transformToLowercase`
- ★★★★☆ `视图: 切换主侧栏可见性` `"ctrl+alt+b"` `workbench.action.toggleSidebarVisibility`
- ★★★☆☆ `搜索编辑器: 选择所有匹配项` `"shift+alt+d"` `selectAllSearchEditorMatches`
- ★★★☆☆ `addCursorsAtSearchResults` `"shift+alt+d"` `addCursorsAtSearchResults`
#### `删除的命令`
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
#### `推荐的命令（除却上述命令）`
- `触发建议` `"ctrl+i"` `editor.action.triggerSuggest`
- `将下一个查找匹配项添加到选择` `"ctrl+d"` `editor.action.addSelectionToNextFindMatch`
- `裁剪尾随空格` `"ctrl+k ctrl+x"` `editor.action.trimTrailingWhitespace`
- `在下面插入行` `"ctrl+enter"` `editor.action.insertLineAfter`
- `在上面插入行` `ctrl+shift+enter` `editor.action.insertLineBefore`
- `格式化文档` `"shift+alt+f"` `editor.action.formatDocument`
- `clangd: Switch Between Source/Header` `"alt+o"` `clangd.switchheadersource`
- `更改语言模式` `"ctrl+k m"` `workbench.action.editor.changeLanguageMode`
- `视图: 切换面板可见性` `"ctrl+j"` `workbench.action.togglePanel`
- `视图: 切换 终端` `"ctrl+backtick"` `workbench.action.terminal.toggleTerminal`
- `终端: 创建新的终端` `"ctrl+shift+backtick"` `workbench.action.terminal.new`
- `工作区: 关闭工作区` `"ctrl+k f"` `workbench.action.closeFolder`
- `重构...` `"ctrl+shift+r"` `editor.action.refactor`
- `转到文件...` `"ctrl+p"` `workbench.action.quickOpen`
- `显示所有命令` `"ctrl+shift+p"` `workbench.action.showCommands`
- `转到行/列...` `"ctrl+g"` `workbench.action.gotoLine`
- `文件: 打开最近的文件…` `"ctrl+r"` `workbench.action.openRecent`
- `Markdown: 打开侧边预览` `"ctrl+k v"` `markdown.showPreviewToSide`
