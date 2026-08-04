
使用表格组织信息
您可以创建表格来组织评论、议题、拉取请求和 wiki 中的信息。

创建表
可以使用竖线 | 和连字符 - 创建表。 连字符用于创建每列的标题，而竖线用于分隔每列。 必须在表格前包含空白链接，以便其正确呈现。


| First Header  | Second Header |
| ------------- | ------------- |
| Content Cell  | Content Cell  |
| Content Cell  | Content Cell  |
在 GitHub 上呈现的两列宽度相等的 Markdown 表的屏幕截图。 标题以粗体呈现，备用内容行具有灰色底纹。

表格末尾的竖线可选。

单元格的宽度可以不同，无需在列内准确对齐。 标题行的第一列中必须至少有三个横线。

| Command | Description |
| --- | --- |
| git status | List all new or modified files |
| git diff | Show file differences that haven't been staged |
在 GitHub 上呈现的两列宽度不同的 Markdown 表的屏幕截图。 行列出命令“git status”和“git diff”及其说明。

如果经常编辑代码片段和表，则可能受益于在 GitHub 上启用对所有注释字段采用固定宽度字体。 有关详细信息，请参阅“关于在 GitHub 上编写和设置格式”。

格式化表格中的内容
可以在表格中使用格式，例如链接、内联代码块和文本样式：

| Command | Description |
| --- | --- |
| `git status` | List all *new or modified* files |
| `git diff` | Show file differences that **haven't been** staged |
在 GitHub 上呈现的两列宽度不同的 Markdown 表的屏幕截图。 命令“git status”和“git diff”将格式设置为代码块。

可以通过在标题行中连字符的左侧、右侧或两侧添加冒号 :，来靠左、靠右或居中对齐列中的文本。

| Left-aligned | Center-aligned | Right-aligned |
| :---         |     :---:      |          ---: |
| git status   | git status     | git status    |
| git diff     | git diff       | git diff      |
具有 GitHub 上呈现的三列的 Markdown 表的屏幕截图，其中显示了如何将单元格中的文本设置为左对齐、居中或右对齐。

若要包含竖线 | 作为单元格中的内容，请在竖线前使用 \：

| Name     | Character |
| ---      | ---       |
| Backtick | `         |
| Pipe     | \|        |
GitHub 上呈现的 Markdown 表的屏幕截图，其中显示了通常关闭单元格的管道在用反斜杠开头时如何在单元格内显示。
