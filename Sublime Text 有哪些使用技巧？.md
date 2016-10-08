
#  [Sublime Text 有哪些使用技巧？](https://zhihu.com/questions/24896283)



[@gyfnice](https://zhihu.com/people/a936693c15ae15cdd2f3f81b7e7b6748)

<b>工欲善其事，必先利其器</b><br><br>我认为Sublime的强大有<b>3</b>方面：<br><ol><li><b>丰富的快捷键组合</b></li><li><b>实用的插件</b></li><li><b>支持代码片段snippet</b></li></ol><br>下面我将从其本身自带的快捷键及插件做出介绍。<br>________________________________________<br><p><b>Sublime快捷键</b></p><p>Sublime原生自带的快捷键也能很大程度上方便开发，这里以Mac为主，windows多数与其相似，以下是Mac下所默认的快捷键：</p><p><strong>Mac</strong></p><p>备注：具体符号对应的按键</p><ul><li><strong>⌘</strong><em>Command key</em></li><li><strong>⌃</strong><em>Control key</em></li><li><strong>⌥</strong><em>Option key</em></li><li><strong>⇧</strong><em>Shift Key</em></li></ul><p>为了方便大家记忆，将快捷键分成了8个类型， 分别为</p><ul><li><em><strong>Edit</strong>(编辑)</em></li><li><em><strong>Selection</strong>(光标选中)</em></li><li><em><strong>Find</strong>(查找）</em></li><li><em><strong>View</strong>(视图)</em></li><li><em><strong>Go to</strong>(跳转)</em></li><li><em><strong>Project</strong>(工程)</em></li><li><em><b>General</b>(通用)</em></li><li><em><b>Tabs</b>(标签)</em></li></ul><div class="highlight"><pre><code class="language-text">Edit(编辑)
</code></pre></div><ul><li><strong>⌘[</strong><em>向左缩进</em> | Left indent</li><li><strong>⌘]</strong><em>向右缩进</em> | Right Indent</li><li><strong>⌘⌃↑</strong><em>与上一行互换（超实用！）</em>| Swap line up</li><li><strong>⌘⌃↓</strong><em>与下一￼行互换￼（超实用！）</em>| Swap line down</li><li><strong>⌘⇧D</strong><em>复制粘贴当前行（减少多余的粘贴）</em>| Duplicate line</li><li><strong>⌘J</strong><em>拼接行（css格式化时挺有用） </em>| join lines</li><li><strong>⌘←</strong><em>去往行的开头</em> | Beginning of line</li><li><strong>⌘→</strong><em>去往行末尾</em> | End of line</li><li><strong>⌘⌃/</strong><em>块注释</em> | Toggle comment block</li><li><strong>⌃K</strong><em>从光标开始的地方删除到行尾</em> | Delete to end</li><li><strong>⌃⇧K</strong><em>删除一整行</em> | delete line</li><li><strong>⌃T</strong><em>相邻单词互换位置，在','前试用，有惊喜（很有趣）</em>| Transpose</li><li><strong>⌘⇧↩</strong><em>向光标前插入一行</em>|insert line before</li><li><strong>⌘↩</strong><em>向光标后插入一行</em>|inter line after</li><li><strong>⌘⌥T</strong><em>插入特殊字符</em>|Special characters</li><li><strong>⌃D</strong><em>向后删除（很怪异的操作，不过感觉很酷炫）</em></li></ul><div class="highlight"><pre><code class="language-text">Selection(光标选中)
</code></pre></div><ul><li><strong>⌘D</strong><em>选中相同的词</em> | Expand selection to words</li><li><strong>⌃⌘G</strong><em>多重文本光标选中（再也不用⌘ D一个一个的找啦）</em>| Expand all selection to words</li><li><strong>⌘L</strong><em>选中一行</em>|Expand selection to line</li><li><strong>Esc</strong><em>单选（取消多重选择）</em>|Single selection,Cancel multiple selections</li><li><strong>⌃⇧↑</strong><em>一行一行向上选中</em>|Add previous line</li><li><strong>⌃⇧↓</strong><em>一行一行向下选中</em>|Add next line</li><li><strong>⌘⇧L</strong><em>将选中的区域分割成多行选中状态(多光标操作状态)</em>|Split into lines</li><li><strong>⌥+拖动鼠标</strong><em>多重光标选中</em></li><li><strong>⌘⇧J</strong><em>已缩进层级为依据，一层层向外选中</em>|Expand selection to indentation</li><li><strong>⌃⇧M</strong><em>将匹配括号中的内容选中</em>|Expand selection to brackets</li></ul><div class="highlight"><pre><code class="language-text">Find(查找)
</code></pre></div><ul><li><strong>⌘F</strong><em>普通查找</em>|Find</li><li><strong>⌘G</strong><em>查找下一个</em>|Find next</li><li><strong>⌘⇧F</strong><em>在文件夹中查找</em>| Find in files</li><li><strong>⌘⇧E</strong><em>缓存用于替换的内容，方便之后的替换</em>|Use selection for replace</li><li><strong>⌘E</strong><em>缓存用于查找的内容，方便之后的查找</em>|Use selection for find</li><li><strong>⌘⌥E</strong><em>一个接一个往下替换</em>|Replace next</li></ul><div class="highlight"><pre><code class="language-text">View(视图)
</code></pre></div><ul><li>推荐使用<strong>Origami插件</strong>，可以随意对sublime进行分割</li></ul><div class="highlight"><pre><code class="language-text">Go to(跳转/定位)
</code></pre></div><ul><li><strong>⌘P</strong><em>跳转文件（很方便）</em>| Go to anything</li><li><strong>⌘R</strong><em>定位文件中的方法@</em>| Go to symbol</li><li><strong>⌘G</strong><em>定位文件中的行号:</em>| Go to line</li><li><strong>⌃M</strong><em>定位匹配的括号</em> | Jump to matching bracket</li><li><strong>⌘F2</strong><em>设置/取消定位标记</em>| Toggle bookmark</li><li><strong>F2</strong><em>跳转到定位标记处</em> | Next bookmark</li><li><strong>⌘⇧F2</strong><em>清除所有定位标记</em>| Clear all bookmarks</li><li><strong>⌘⌥→</strong><em>下一个打开的文件</em>| Next file</li></ul><div class="highlight"><pre><code class="language-text">Project(工程)
</code></pre></div><ul><li><strong>⌘⌃P</strong><em>在保存过的工程中切换，随意变换工程环境</em>|Switch project window</li></ul><div class="highlight"><pre><code class="language-text">General(通用)
</code></pre></div><ul><li><b>⌘⇧P </b><i>打开命令行</i><b>| </b>Command prompt<br></li><li><b>⌘K, ⌘B</b><i>隐藏/打开 侧边栏| Toggle side bar</i></li></ul><div class="highlight"><pre><code class="language-text">Tabs（标签栏）
</code></pre></div><ul><li><b>⌘⇧t</b><i> 打开最后一次关闭的文件|Open last closed tab</i></li><li><b>^Tab</b><i> 循环遍历tab|Cycle up through tabs<br></i></li><li><b>^<b>⇧</b>Tab</b><i> 反方向循环遍历tab|Cycle down through tabs</i></li></ul>_____________________________________<br><b><i>实用插件</i><br></b><p>Sublime里有些插件十分强大，在这里我推荐我最喜欢的几个：</p><p>首推<br></p><p><b><u>Emmet</u></b>:这个插件内置的功能很强大，它的快捷键详细说明如下：</p><ul><li>操作、编辑HTML：<a href="http://link.zhihu.com/?target=http%3A//docs.emmet.io/" class=" wrap external" target="_blank" rel="nofollow noreferrer">Emmet Documentation<i class="icon-external"></i></a><br></li><li>快速生成html语法篇：<a href="http://link.zhihu.com/?target=http%3A//docs.emmet.io/cheat-sheet/" class=" wrap external" target="_blank" rel="nofollow noreferrer">Cheat Sheet<i class="icon-external"></i></a><br></li><li>理解记忆后，能增加很多开发效率。<br></li></ul><br><p><b><u>Modific</u></b>: <a href="http://link.zhihu.com/?target=http%3A//github.com/gornostal/Modific" class=" wrap external" target="_blank" rel="nofollow noreferrer">gornostal/Modific · GitHub<i class="icon-external"></i></a></p><blockquote>Highlight lines changed since the last commit </blockquote><p><i>无论git，还是svn 只要一保存，都能标出代码的改动状态，超赞</i></p><img src="http://pic3.zhimg.com/50/f7e5f75f86d689c1ab13f1ccafadc502_b.jpg" data-rawwidth="215" data-rawheight="337" class="content_image" width="215"><br><p><b><u>Tag</u></b>: HTML格式化</p><br><p><b><u>jsformat</u></b>: javascript格式化</p><br><u><b>Origami：</b>Sublime视图设置</u><a href="http://link.zhihu.com/?target=http%3A//github.com/SublimeText/Origami" class=" wrap external" target="_blank" rel="nofollow noreferrer">SublimeText/Origami · GitHub<i class="icon-external"></i></a><br><br>_____________________________________<br><p><strong>代码片段</strong></p><p>常用的都在这里能找到，有其它需要就自己配吧：</p><p><a href="http://link.zhihu.com/?target=http%3A//github.com/gyfnice/javascript/tree/sublime-snippets/snippets/sublime/javascript" class=" wrap external" target="_blank" rel="nofollow noreferrer">javascript/snippets/sublime/javascript at sublime-snippets · gyfnice/javascript · GitHub<i class="icon-external"></i></a></p><p><strong>总结:</strong></p><p><strong>这里面有些快捷键单兵作战能力可能不强，但如果你能灵活使用，将它们配合起来，能发挥很大的威力。</strong></p><p><strong>可能你会觉得快捷键有些多，记不下来，但是只要坚持使用，把它变为习惯，你的开发效率肯定会得到提高的！</strong></p><blockquote><p>希望对大家有帮助，有疑问的可以单独私信。</p></blockquote><div class="highlight"><pre><code class="language-text">尾声：windows下的快捷键一览
</code></pre></div><blockquote><div class="highlight"><pre><code class="language-text">Alt+R : 开启正则表达式功能
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
Alt + [NUM]	Switch to tab number [NUM] where [NUM] &lt;= number of tabs
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
</code></pre></div></blockquote>