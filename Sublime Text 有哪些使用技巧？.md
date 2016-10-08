
#  [Sublime Text 有哪些使用技巧？](https://zhihu.com/questions/24896283)



[@gyfnice](https://zhihu.com/people/a936693c15ae15cdd2f3f81b7e7b6748)

&lt;b&gt;工欲善其事，必先利其器&lt;/b&gt;&lt;br&gt;&lt;br&gt;我认为Sublime的强大有&lt;b&gt;3&lt;/b&gt;方面：&lt;br&gt;&lt;ol&gt;&lt;li&gt;&lt;b&gt;丰富的快捷键组合&lt;/b&gt;&lt;/li&gt;&lt;li&gt;&lt;b&gt;实用的插件&lt;/b&gt;&lt;/li&gt;&lt;li&gt;&lt;b&gt;支持代码片段snippet&lt;/b&gt;&lt;/li&gt;&lt;/ol&gt;&lt;br&gt;下面我将从其本身自带的快捷键及插件做出介绍。&lt;br&gt;________________________________________&lt;br&gt;&lt;p&gt;&lt;b&gt;Sublime快捷键&lt;/b&gt;&lt;/p&gt;&lt;p&gt;Sublime原生自带的快捷键也能很大程度上方便开发，这里以Mac为主，windows多数与其相似，以下是Mac下所默认的快捷键：&lt;/p&gt;&lt;p&gt;&lt;strong&gt;Mac&lt;/strong&gt;&lt;/p&gt;&lt;p&gt;备注：具体符号对应的按键&lt;/p&gt;&lt;ul&gt;&lt;li&gt;&lt;strong&gt;⌘&lt;/strong&gt;&lt;em&gt;Command key&lt;/em&gt;&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌃&lt;/strong&gt;&lt;em&gt;Control key&lt;/em&gt;&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌥&lt;/strong&gt;&lt;em&gt;Option key&lt;/em&gt;&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⇧&lt;/strong&gt;&lt;em&gt;Shift Key&lt;/em&gt;&lt;/li&gt;&lt;/ul&gt;&lt;p&gt;为了方便大家记忆，将快捷键分成了8个类型， 分别为&lt;/p&gt;&lt;ul&gt;&lt;li&gt;&lt;em&gt;&lt;strong&gt;Edit&lt;/strong&gt;(编辑)&lt;/em&gt;&lt;/li&gt;&lt;li&gt;&lt;em&gt;&lt;strong&gt;Selection&lt;/strong&gt;(光标选中)&lt;/em&gt;&lt;/li&gt;&lt;li&gt;&lt;em&gt;&lt;strong&gt;Find&lt;/strong&gt;(查找）&lt;/em&gt;&lt;/li&gt;&lt;li&gt;&lt;em&gt;&lt;strong&gt;View&lt;/strong&gt;(视图)&lt;/em&gt;&lt;/li&gt;&lt;li&gt;&lt;em&gt;&lt;strong&gt;Go to&lt;/strong&gt;(跳转)&lt;/em&gt;&lt;/li&gt;&lt;li&gt;&lt;em&gt;&lt;strong&gt;Project&lt;/strong&gt;(工程)&lt;/em&gt;&lt;/li&gt;&lt;li&gt;&lt;em&gt;&lt;b&gt;General&lt;/b&gt;(通用)&lt;/em&gt;&lt;/li&gt;&lt;li&gt;&lt;em&gt;&lt;b&gt;Tabs&lt;/b&gt;(标签)&lt;/em&gt;&lt;/li&gt;&lt;/ul&gt;&lt;div class=&#34;highlight&#34;&gt;&lt;pre&gt;&lt;code class=&#34;language-text&#34;&gt;Edit(编辑)
&lt;/code&gt;&lt;/pre&gt;&lt;/div&gt;&lt;ul&gt;&lt;li&gt;&lt;strong&gt;⌘[&lt;/strong&gt;&lt;em&gt;向左缩进&lt;/em&gt; | Left indent&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌘]&lt;/strong&gt;&lt;em&gt;向右缩进&lt;/em&gt; | Right Indent&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌘⌃↑&lt;/strong&gt;&lt;em&gt;与上一行互换（超实用！）&lt;/em&gt;| Swap line up&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌘⌃↓&lt;/strong&gt;&lt;em&gt;与下一￼行互换￼（超实用！）&lt;/em&gt;| Swap line down&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌘⇧D&lt;/strong&gt;&lt;em&gt;复制粘贴当前行（减少多余的粘贴）&lt;/em&gt;| Duplicate line&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌘J&lt;/strong&gt;&lt;em&gt;拼接行（css格式化时挺有用） &lt;/em&gt;| join lines&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌘←&lt;/strong&gt;&lt;em&gt;去往行的开头&lt;/em&gt; | Beginning of line&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌘→&lt;/strong&gt;&lt;em&gt;去往行末尾&lt;/em&gt; | End of line&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌘⌃/&lt;/strong&gt;&lt;em&gt;块注释&lt;/em&gt; | Toggle comment block&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌃K&lt;/strong&gt;&lt;em&gt;从光标开始的地方删除到行尾&lt;/em&gt; | Delete to end&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌃⇧K&lt;/strong&gt;&lt;em&gt;删除一整行&lt;/em&gt; | delete line&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌃T&lt;/strong&gt;&lt;em&gt;相邻单词互换位置，在&#39;,&#39;前试用，有惊喜（很有趣）&lt;/em&gt;| Transpose&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌘⇧↩&lt;/strong&gt;&lt;em&gt;向光标前插入一行&lt;/em&gt;|insert line before&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌘↩&lt;/strong&gt;&lt;em&gt;向光标后插入一行&lt;/em&gt;|inter line after&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌘⌥T&lt;/strong&gt;&lt;em&gt;插入特殊字符&lt;/em&gt;|Special characters&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌃D&lt;/strong&gt;&lt;em&gt;向后删除（很怪异的操作，不过感觉很酷炫）&lt;/em&gt;&lt;/li&gt;&lt;/ul&gt;&lt;div class=&#34;highlight&#34;&gt;&lt;pre&gt;&lt;code class=&#34;language-text&#34;&gt;Selection(光标选中)
&lt;/code&gt;&lt;/pre&gt;&lt;/div&gt;&lt;ul&gt;&lt;li&gt;&lt;strong&gt;⌘D&lt;/strong&gt;&lt;em&gt;选中相同的词&lt;/em&gt; | Expand selection to words&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌃⌘G&lt;/strong&gt;&lt;em&gt;多重文本光标选中（再也不用⌘ D一个一个的找啦）&lt;/em&gt;| Expand all selection to words&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌘L&lt;/strong&gt;&lt;em&gt;选中一行&lt;/em&gt;|Expand selection to line&lt;/li&gt;&lt;li&gt;&lt;strong&gt;Esc&lt;/strong&gt;&lt;em&gt;单选（取消多重选择）&lt;/em&gt;|Single selection,Cancel multiple selections&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌃⇧↑&lt;/strong&gt;&lt;em&gt;一行一行向上选中&lt;/em&gt;|Add previous line&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌃⇧↓&lt;/strong&gt;&lt;em&gt;一行一行向下选中&lt;/em&gt;|Add next line&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌘⇧L&lt;/strong&gt;&lt;em&gt;将选中的区域分割成多行选中状态(多光标操作状态)&lt;/em&gt;|Split into lines&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌥+拖动鼠标&lt;/strong&gt;&lt;em&gt;多重光标选中&lt;/em&gt;&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌘⇧J&lt;/strong&gt;&lt;em&gt;已缩进层级为依据，一层层向外选中&lt;/em&gt;|Expand selection to indentation&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌃⇧M&lt;/strong&gt;&lt;em&gt;将匹配括号中的内容选中&lt;/em&gt;|Expand selection to brackets&lt;/li&gt;&lt;/ul&gt;&lt;div class=&#34;highlight&#34;&gt;&lt;pre&gt;&lt;code class=&#34;language-text&#34;&gt;Find(查找)
&lt;/code&gt;&lt;/pre&gt;&lt;/div&gt;&lt;ul&gt;&lt;li&gt;&lt;strong&gt;⌘F&lt;/strong&gt;&lt;em&gt;普通查找&lt;/em&gt;|Find&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌘G&lt;/strong&gt;&lt;em&gt;查找下一个&lt;/em&gt;|Find next&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌘⇧F&lt;/strong&gt;&lt;em&gt;在文件夹中查找&lt;/em&gt;| Find in files&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌘⇧E&lt;/strong&gt;&lt;em&gt;缓存用于替换的内容，方便之后的替换&lt;/em&gt;|Use selection for replace&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌘E&lt;/strong&gt;&lt;em&gt;缓存用于查找的内容，方便之后的查找&lt;/em&gt;|Use selection for find&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌘⌥E&lt;/strong&gt;&lt;em&gt;一个接一个往下替换&lt;/em&gt;|Replace next&lt;/li&gt;&lt;/ul&gt;&lt;div class=&#34;highlight&#34;&gt;&lt;pre&gt;&lt;code class=&#34;language-text&#34;&gt;View(视图)
&lt;/code&gt;&lt;/pre&gt;&lt;/div&gt;&lt;ul&gt;&lt;li&gt;推荐使用&lt;strong&gt;Origami插件&lt;/strong&gt;，可以随意对sublime进行分割&lt;/li&gt;&lt;/ul&gt;&lt;div class=&#34;highlight&#34;&gt;&lt;pre&gt;&lt;code class=&#34;language-text&#34;&gt;Go to(跳转/定位)
&lt;/code&gt;&lt;/pre&gt;&lt;/div&gt;&lt;ul&gt;&lt;li&gt;&lt;strong&gt;⌘P&lt;/strong&gt;&lt;em&gt;跳转文件（很方便）&lt;/em&gt;| Go to anything&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌘R&lt;/strong&gt;&lt;em&gt;定位文件中的方法@&lt;/em&gt;| Go to symbol&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌘G&lt;/strong&gt;&lt;em&gt;定位文件中的行号:&lt;/em&gt;| Go to line&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌃M&lt;/strong&gt;&lt;em&gt;定位匹配的括号&lt;/em&gt; | Jump to matching bracket&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌘F2&lt;/strong&gt;&lt;em&gt;设置/取消定位标记&lt;/em&gt;| Toggle bookmark&lt;/li&gt;&lt;li&gt;&lt;strong&gt;F2&lt;/strong&gt;&lt;em&gt;跳转到定位标记处&lt;/em&gt; | Next bookmark&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌘⇧F2&lt;/strong&gt;&lt;em&gt;清除所有定位标记&lt;/em&gt;| Clear all bookmarks&lt;/li&gt;&lt;li&gt;&lt;strong&gt;⌘⌥→&lt;/strong&gt;&lt;em&gt;下一个打开的文件&lt;/em&gt;| Next file&lt;/li&gt;&lt;/ul&gt;&lt;div class=&#34;highlight&#34;&gt;&lt;pre&gt;&lt;code class=&#34;language-text&#34;&gt;Project(工程)
&lt;/code&gt;&lt;/pre&gt;&lt;/div&gt;&lt;ul&gt;&lt;li&gt;&lt;strong&gt;⌘⌃P&lt;/strong&gt;&lt;em&gt;在保存过的工程中切换，随意变换工程环境&lt;/em&gt;|Switch project window&lt;/li&gt;&lt;/ul&gt;&lt;div class=&#34;highlight&#34;&gt;&lt;pre&gt;&lt;code class=&#34;language-text&#34;&gt;General(通用)
&lt;/code&gt;&lt;/pre&gt;&lt;/div&gt;&lt;ul&gt;&lt;li&gt;&lt;b&gt;⌘⇧P &lt;/b&gt;&lt;i&gt;打开命令行&lt;/i&gt;&lt;b&gt;| &lt;/b&gt;Command prompt&lt;br&gt;&lt;/li&gt;&lt;li&gt;&lt;b&gt;⌘K, ⌘B&lt;/b&gt;&lt;i&gt;隐藏/打开 侧边栏| Toggle side bar&lt;/i&gt;&lt;/li&gt;&lt;/ul&gt;&lt;div class=&#34;highlight&#34;&gt;&lt;pre&gt;&lt;code class=&#34;language-text&#34;&gt;Tabs（标签栏）
&lt;/code&gt;&lt;/pre&gt;&lt;/div&gt;&lt;ul&gt;&lt;li&gt;&lt;b&gt;⌘⇧t&lt;/b&gt;&lt;i&gt; 打开最后一次关闭的文件|Open last closed tab&lt;/i&gt;&lt;/li&gt;&lt;li&gt;&lt;b&gt;^Tab&lt;/b&gt;&lt;i&gt; 循环遍历tab|Cycle up through tabs&lt;br&gt;&lt;/i&gt;&lt;/li&gt;&lt;li&gt;&lt;b&gt;^&lt;b&gt;⇧&lt;/b&gt;Tab&lt;/b&gt;&lt;i&gt; 反方向循环遍历tab|Cycle down through tabs&lt;/i&gt;&lt;/li&gt;&lt;/ul&gt;_____________________________________&lt;br&gt;&lt;b&gt;&lt;i&gt;实用插件&lt;/i&gt;&lt;br&gt;&lt;/b&gt;&lt;p&gt;Sublime里有些插件十分强大，在这里我推荐我最喜欢的几个：&lt;/p&gt;&lt;p&gt;首推&lt;br&gt;&lt;/p&gt;&lt;p&gt;&lt;b&gt;&lt;u&gt;Emmet&lt;/u&gt;&lt;/b&gt;:这个插件内置的功能很强大，它的快捷键详细说明如下：&lt;/p&gt;&lt;ul&gt;&lt;li&gt;操作、编辑HTML：&lt;a href=&#34;http://link.zhihu.com/?target=http%3A//docs.emmet.io/&#34; class=&#34; wrap external&#34; target=&#34;_blank&#34; rel=&#34;nofollow noreferrer&#34;&gt;Emmet Documentation&lt;i class=&#34;icon-external&#34;&gt;&lt;/i&gt;&lt;/a&gt;&lt;br&gt;&lt;/li&gt;&lt;li&gt;快速生成html语法篇：&lt;a href=&#34;http://link.zhihu.com/?target=http%3A//docs.emmet.io/cheat-sheet/&#34; class=&#34; wrap external&#34; target=&#34;_blank&#34; rel=&#34;nofollow noreferrer&#34;&gt;Cheat Sheet&lt;i class=&#34;icon-external&#34;&gt;&lt;/i&gt;&lt;/a&gt;&lt;br&gt;&lt;/li&gt;&lt;li&gt;理解记忆后，能增加很多开发效率。&lt;br&gt;&lt;/li&gt;&lt;/ul&gt;&lt;br&gt;&lt;p&gt;&lt;b&gt;&lt;u&gt;Modific&lt;/u&gt;&lt;/b&gt;: &lt;a href=&#34;http://link.zhihu.com/?target=http%3A//github.com/gornostal/Modific&#34; class=&#34; wrap external&#34; target=&#34;_blank&#34; rel=&#34;nofollow noreferrer&#34;&gt;gornostal/Modific · GitHub&lt;i class=&#34;icon-external&#34;&gt;&lt;/i&gt;&lt;/a&gt;&lt;/p&gt;&lt;blockquote&gt;Highlight lines changed since the last commit &lt;/blockquote&gt;&lt;p&gt;&lt;i&gt;无论git，还是svn 只要一保存，都能标出代码的改动状态，超赞&lt;/i&gt;&lt;/p&gt;&lt;img src=&#34;http://pic3.zhimg.com/50/f7e5f75f86d689c1ab13f1ccafadc502_b.jpg&#34; data-rawwidth=&#34;215&#34; data-rawheight=&#34;337&#34; class=&#34;content_image&#34; width=&#34;215&#34;&gt;&lt;br&gt;&lt;p&gt;&lt;b&gt;&lt;u&gt;Tag&lt;/u&gt;&lt;/b&gt;: HTML格式化&lt;/p&gt;&lt;br&gt;&lt;p&gt;&lt;b&gt;&lt;u&gt;jsformat&lt;/u&gt;&lt;/b&gt;: javascript格式化&lt;/p&gt;&lt;br&gt;&lt;u&gt;&lt;b&gt;Origami：&lt;/b&gt;Sublime视图设置&lt;/u&gt;&lt;a href=&#34;http://link.zhihu.com/?target=http%3A//github.com/SublimeText/Origami&#34; class=&#34; wrap external&#34; target=&#34;_blank&#34; rel=&#34;nofollow noreferrer&#34;&gt;SublimeText/Origami · GitHub&lt;i class=&#34;icon-external&#34;&gt;&lt;/i&gt;&lt;/a&gt;&lt;br&gt;&lt;br&gt;_____________________________________&lt;br&gt;&lt;p&gt;&lt;strong&gt;代码片段&lt;/strong&gt;&lt;/p&gt;&lt;p&gt;常用的都在这里能找到，有其它需要就自己配吧：&lt;/p&gt;&lt;p&gt;&lt;a href=&#34;http://link.zhihu.com/?target=http%3A//github.com/gyfnice/javascript/tree/sublime-snippets/snippets/sublime/javascript&#34; class=&#34; wrap external&#34; target=&#34;_blank&#34; rel=&#34;nofollow noreferrer&#34;&gt;javascript/snippets/sublime/javascript at sublime-snippets · gyfnice/javascript · GitHub&lt;i class=&#34;icon-external&#34;&gt;&lt;/i&gt;&lt;/a&gt;&lt;/p&gt;&lt;p&gt;&lt;strong&gt;总结:&lt;/strong&gt;&lt;/p&gt;&lt;p&gt;&lt;strong&gt;这里面有些快捷键单兵作战能力可能不强，但如果你能灵活使用，将它们配合起来，能发挥很大的威力。&lt;/strong&gt;&lt;/p&gt;&lt;p&gt;&lt;strong&gt;可能你会觉得快捷键有些多，记不下来，但是只要坚持使用，把它变为习惯，你的开发效率肯定会得到提高的！&lt;/strong&gt;&lt;/p&gt;&lt;blockquote&gt;&lt;p&gt;希望对大家有帮助，有疑问的可以单独私信。&lt;/p&gt;&lt;/blockquote&gt;&lt;div class=&#34;highlight&#34;&gt;&lt;pre&gt;&lt;code class=&#34;language-text&#34;&gt;尾声：windows下的快捷键一览
&lt;/code&gt;&lt;/pre&gt;&lt;/div&gt;&lt;blockquote&gt;&lt;div class=&#34;highlight&#34;&gt;&lt;pre&gt;&lt;code class=&#34;language-text&#34;&gt;Alt+R : 开启正则表达式功能
Alt+Enter: 找到匹配目标后全部选择
Ctrl+R：前往 method（mac下⌘R）
Ctrl+M：跳转到对应括号
按Ctrl+Shift+上下键，可替换行
Ctrl+D：选择单词，重复可增加选择下一个相同的单词
Ctrl+L：选择行，重复可依次增加选择下一行
Ctrl+Shift+P：打开命令面板
Ctrl+P：搜索项目中的文件（mac下⌘P），在里面输入：
admi@auto 可以定位到相应文件夹(admin.html)下的相应方法（auto）。
Ctrl+G：跳转到第几行
Ctrl+W：关闭当前打开文件
Ctrl+Shift+W：关闭所有打开文件
Ctrl+Shift+V：粘贴并格式化
Ctrl+Shift+L：选择多行
Ctrl+Shift+Enter：在当前行前插入新行
Ctrl+X：删除当前行
Ctrl+U：软撤销，撤销光标位置
Ctrl+J：选择标签内容
Ctrl+F：查找内容
Ctrl+Shift+F：查找并替换
Ctrl+H：替换
Ctrl+N：新建窗口
Ctrl+K+B：开关侧栏
Ctrl+Shift+M：选中当前括号内容，重复可选着括号本身
Ctrl+F2：设置/删除标记
Ctrl+/：注释当前行
Ctrl+Shift+/：当前位置插入注释
Ctrl+Alt+/：块注释，并Focus到首行，写注释说明用的
Ctrl+Shift+A：选择当前标签前后，修改标签用的
F11：全屏
Shift+F11：全屏免打扰模式，只编辑当前文件
Alt+F3：选择所有相同的词
Alt+.：闭合标签
Alt+Shift+数字：分屏显示
Alt+数字：切换打开第N个文件
Shift+右键拖动：光标多不，用来更改或插入列内容
鼠标的前进后退键可切换Tab文件
按Ctrl，依次点击或选取，可需要编辑的多个位置
Ctrl+shift+D: 备份多个当前行
Ctrl+shift+T: 恢复已经关闭的标签

Editing
Keypress	Command
Ctrl + X	Delete line
Ctrl + ↩	Insert line after
Ctrl + ⇧ + ↩	Insert line before
Ctrl + ⇧ + ↑	Move line/selection up
Ctrl + ⇧ + ↓	Move line/selection down
Ctrl + L	Select line - Repeat to select next lines
Ctrl + D	Select word - Repeat select others occurrences
Ctrl + M	Jump to closing parentheses Repeat to jump to opening parentheses
Ctrl + ⇧ + M	Select all contents of the current parentheses
Ctrl + KK	Delete from cursor to end of line
Ctrl + K + ⌫	Delete from cursor to start of line
Ctrl + ]	Indent current line(s)
Ctrl + [	Un-indent current line(s)
Ctrl + ⇧ + D	Duplicate line(s)
Ctrl + J	Join line below to the end of the current line
Ctrl + /	Comment/un-comment current line
Ctrl + ⇧ + /	Block comment current selection
Ctrl + Y	Redo, or repeat last keyboard shortcut command
Ctrl + ⇧ + V	Paste and indent correctly
Ctrl + Space	Select next auto-complete suggestion
Ctrl + U	soft undo; jumps to your last change before undoing change when repeated
Windows
Ctrl + Alt + Up	Column selection up
Ctrl + Alt + Down	Column selection down
Linux
Alt + ⇧ + Up	Column selection up
Alt + ⇧ + Down	Column selection up
Navigation/Goto Anywhere
Keypress	Command
Ctrl + P	Quick-open files by name
Ctrl + R	Goto symbol
Ctrl + ;	Goto word in current file
Ctrl + G	Goto line in current file
General
Keypress	Command
Ctrl + ⇧ + P	Command prompt
Ctrl + KB	Toggle side bar
Ctrl + ⇧ + Alt + P	Show scope in status bar
Find/Replace
Keypress	Command
Ctrl + F	Find
Ctrl + H	Replace
Ctrl + ⇧ + F	Find in files
Tabs
Keypress	Command
Ctrl + ⇧ + t	Open last closed tab
Ctrl + PgUp	Cycle up through tabs
Ctrl + PgDn	Cycle down through tabs
Ctrl + ⇆	Find in files
Alt + [NUM]	Switch to tab number [NUM] where [NUM] &amp;lt;= number of tabs
Split window
Keypress	Command
Alt + ⇧ + 2	Split view into two columns
Alt + ⇧ + 1	Revert view to single column
Alt + ⇧ + 5	Set view to grid (4 groups)
Ctrl + [NUM]	Jump to group where num is 1-4
Ctrl + ⇧ + [NUM]	Move file to specified group where num is 1-4
Bookmarks
Keypress	Command
Ctrl + F2	Toggle bookmark
F2	Next bookmark
⇧ + F2	Previous bookmark
Ctrl + ⇧ + F2	Clear bookmarks
Text manipulation
Keypress	Command
Ctrl + KU	Transform to Uppercase
Ctrl + KL	Transform to Lowercase
&lt;/code&gt;&lt;/pre&gt;&lt;/div&gt;&lt;/blockquote&gt;