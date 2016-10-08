
#  [从零开始的 Redux 教程](https://zhihu.com/articles/22770986)


[@codefalling](https://zhihu.com/people/676f5d8a5e884fcdf6c977aafbb0d99a)

<h2>前言</h2><p>前端生态日新月异, flux 已经过时（恩然而我都还没有来得及学），redux 成了状态管理的标配，每一个前端开发者都应该学习。然而因为 redux 的多种概念着实让新手费解，很多人沉浸在 react 全家桶的配置无法自拔。所以我试着丢开 react，理清楚 redux 本身的几个主要概念，并争取循序渐进的讲解 redux 各种概念的用法和意义。</p><h2>从零开始</h2><p>一次性引入过多的新东西会让人不知所措，所以我们尽可能的减轻依赖。同时为了避免新人掉进环境配置(npm install)的大坑，我们直接采用<a href="http://link.zhihu.com/?target=http%3A//jsfiddle.net/" class=" wrap external" target="_blank" rel="nofollow noreferrer">Create a new fiddle<i class="icon-external"></i></a> 来实践。</p><p>新建一个 jsfiddle，将语言设为 Babel，在左侧的 External Resources 直接引入 redux: <a href="http://link.zhihu.com/?target=http%3A//cdnjs.cloudflare.com/ajax/libs/redux/3.6.0/redux.min.js" class=" external" target="_blank" rel="nofollow noreferrer"><span class="invisible">http://</span><span class="visible">cdnjs.cloudflare.com/aj</span><span class="invisible">ax/libs/redux/3.6.0/redux.min.js</span><span class="ellipsis"></span><i class="icon-external"></i></a>。记得打开开发者工具，方便看到报错和后面的输出。</p><p>目前为止这么多足以，不需要引入 react 或者任何其他东西。</p><h2>最简单的例子</h2><p>很多教程喜欢一开始就把 redux 里的几个概念拆开讲，每个概念又贴上大段大段的代码，弄得人一头雾水。而我们因为暂时丢掉了 react，得以用一个足够简单却完整的例子讲解 redux 的工作流程。</p><div class="highlight"><pre><code class="language-text"><span></span>// 这里是因为直接引入了 js 才用这种写法，当本地使用 webpack 时我们应该使用 import { createStore, applyMiddleware  } from 'redux'
const { createStore, applyMiddleware } = Redux

const reducer = (state, action) =&gt; {  
  let result = state
  switch (action.type) {
    case "INC":
      result += action.payload
      break;
    case "DEC":
      result -= action.payload
      break;
  }
  return result
}

const logger = store =&gt; next =&gt; action =&gt; {  
  console.log('dispatching', action)
  let result = next(action)
  console.log('next state', store.getState())
  return result
}

const store = createStore(reducer, 0, applyMiddleware(logger))

store.dispatch({type: 'INC', payload: 1})  
store.dispatch({type: 'INC', payload: 2})  
store.dispatch({type: 'DEC', payload: 5})  
</code></pre></div><p>观察控制台，我们得到的输出是：</p><div class="highlight"><pre><code class="language-js"><span></span><span class="nx">dispatching</span> <span class="nb">Object</span> <span class="p">{</span><span class="nx">type</span><span class="o">:</span> <span class="s2">"INC"</span><span class="p">,</span> <span class="nx">payload</span><span class="o">:</span> <span class="mi">1</span><span class="p">}</span>  
<span class="nx">next</span> <span class="nx">state</span> <span class="mi">1</span>  
<span class="nx">dispatching</span> <span class="nb">Object</span> <span class="p">{</span><span class="nx">type</span><span class="o">:</span> <span class="s2">"INC"</span><span class="p">,</span> <span class="nx">payload</span><span class="o">:</span> <span class="mi">2</span><span class="p">}</span>  
<span class="nx">next</span> <span class="nx">state</span> <span class="mi">3</span>  
<span class="nx">dispatching</span> <span class="nb">Object</span> <span class="p">{</span><span class="nx">type</span><span class="o">:</span> <span class="s2">"DEC"</span><span class="p">,</span> <span class="nx">payload</span><span class="o">:</span> <span class="mi">5</span><span class="p">}</span>  
<span class="nx">next</span> <span class="nx">state</span> <span class="o">-</span><span class="mi">2</span>  
</code></pre></div><p>这个短小的例子已经用到了我们要讲的几个主要概念，reducer、store、middleware、action。</p><p>store 负责状态的存储，需要注意的是，在 redux 中只有一个 store，而如何在一个 store 中维护众多的状态，我们后面会提到。</p><p>action 则类似触发事件，使用 store.dispatch 发送出去，必须要有一个 type 属性。同时 action 也可以附带其他数据，例如上面代码里的 payload。</p><p>reducer 在每次有新的 action 时被触发，则只做一件事情，就是收到当前的 state 和 action，并且返回一个全新的 state。</p><p>middleware 则发生在每次 action dispatch 后，reducer 触发前，在 middleware 中调用 next(action) 才会将 action 传递给 reducer 并且返回新的结果。这种设计可以让我们很灵活的实现一些针对所有 action 的功能，例如 log 或者针对特定类型的 action 做一些处理等。</p><p>这样，整个 redux 就相当于一个状态机，新的 action 被触发，经过 middleware，由 reducer 产生新的状态。</p><p>我特意没有把他们画成一个循环，因为 state 是不应该改变的，只是由 reducer 返回新的 state。也正以为这个原因，我们在使用 redux 开发应用时，可以很轻松地跟踪到状态的变化，将状态直接 revert 到某个点，撤销这一类的功能非常容易实现。</p><img src="http://pic3.zhimg.com/v2-763da8e4884fb15607354524520f49fa_b.png" data-rawwidth="436" data-rawheight="513" class="origin_image zh-lightbox-thumb" width="436" data-original="http://pic3.zhimg.com/v2-763da8e4884fb15607354524520f49fa_r.png"><br><h2>immutable</h2><p>上面我们提到，state 不会改变，而是由 reducer 返回新的 state。这样我们称 state 是 immutable 的。但是 JavaScript 本身没有提供这个特性，我们需要使用一些和平时不同的写法来达到这个目的。在更详细地介绍 redux 的各个概念前，我们先来了解一下 immutable。</p><p>immutable 和 const 不是一个含义，const 指的是标识符对应的值不可被改变，例如</p><div class="highlight"><pre><code class="language-js"><span></span><span class="kr">const</span> <span class="nx">a</span> <span class="o">=</span> <span class="mi">3</span>  
<span class="nx">a</span> <span class="o">=</span> <span class="mi">4</span>  
</code></pre></div><p>会抛出一个异常，表示 a 不能被修改。</p><p>而 immutable 则指的是值本身不能被修改，例如在 JavaScript 中的 string 和 number 等基本类型都是不能被修改的，但 object 和 array 则不是。</p><div class="highlight"><pre><code class="language-js"><span></span><span class="nx">a</span> <span class="o">=</span> <span class="s1">'I am string'</span>  
<span class="nx">b</span> <span class="o">=</span> <span class="nx">a</span>  
<span class="nx">b</span> <span class="o">=</span> <span class="s1">'Oh yes'</span>

<span class="nx">c</span> <span class="o">=</span> <span class="p">{</span><span class="nx">name</span><span class="o">:</span> <span class="s2">"Li"</span><span class="p">}</span>  
<span class="nx">d</span> <span class="o">=</span> <span class="nx">c</span>  
<span class="nx">d</span><span class="p">.</span><span class="nx">name</span> <span class="o">=</span> <span class="s1">'K'</span>

<span class="nx">console</span><span class="p">.</span><span class="nx">log</span><span class="p">(</span><span class="nx">a</span><span class="p">)</span> <span class="c1">// "I am string"  </span>
<span class="nx">console</span><span class="p">.</span><span class="nx">log</span><span class="p">(</span><span class="nx">b</span><span class="p">)</span> <span class="c1">// "Oh yes"  </span>
<span class="nx">console</span><span class="p">.</span><span class="nx">log</span><span class="p">(</span><span class="nx">c</span><span class="p">)</span> <span class="c1">// {name: "K"}  </span>
<span class="nx">console</span><span class="p">.</span><span class="nx">log</span><span class="p">(</span><span class="nx">d</span><span class="p">)</span> <span class="c1">// {name: "K"}  </span>
</code></pre></div><p>可以看到对象的内容被改变了。所以在处理对象和数组的时候，我们需要注意一些，只使用没有副作用（side effect）的操作：</p><div class="highlight"><pre><code class="language-js"><span></span><span class="nx">c</span> <span class="o">=</span> <span class="p">{</span><span class="nx">name</span><span class="o">:</span> <span class="s2">"Li"</span><span class="p">,</span> <span class="nx">age</span><span class="o">:</span> <span class="mi">17</span><span class="p">}</span>  
<span class="nx">d</span> <span class="o">=</span> <span class="p">{...</span><span class="nx">c</span><span class="p">,</span> <span class="nx">name</span><span class="o">:</span> <span class="s2">"K"</span><span class="p">}</span>  
<span class="nx">e</span> <span class="o">=</span> <span class="p">[</span><span class="mi">2</span><span class="p">,</span> <span class="mi">4</span><span class="p">,</span> <span class="mi">6</span><span class="p">]</span>  
<span class="nx">f</span> <span class="o">=</span> <span class="nx">e</span><span class="p">.</span><span class="nx">slice</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="mi">1</span><span class="p">).</span><span class="nx">concat</span><span class="p">(</span><span class="nx">e</span><span class="p">.</span><span class="nx">slice</span><span class="p">(</span><span class="mi">2</span><span class="p">))</span>

<span class="nx">console</span><span class="p">.</span><span class="nx">log</span><span class="p">(</span><span class="nx">c</span><span class="p">)</span> <span class="c1">// {name: "Li", age: 17}  </span>
<span class="nx">console</span><span class="p">.</span><span class="nx">log</span><span class="p">(</span><span class="nx">d</span><span class="p">)</span> <span class="c1">// {name: "K", age: 17}  </span>
<span class="nx">console</span><span class="p">.</span><span class="nx">log</span><span class="p">(</span><span class="nx">e</span><span class="p">)</span> <span class="c1">// [2, 4, 6]  </span>
<span class="nx">console</span><span class="p">.</span><span class="nx">log</span><span class="p">(</span><span class="nx">f</span><span class="p">)</span> <span class="c1">// [2, 6]  </span>
</code></pre></div><p>当然，我们也可以使用 immutable.js 等库来解决这个问题。</p><h2>一步步改进</h2><p>了解了 immutable 后我们可以学习更加复杂的 reducer。上面的例子中整个 state 只是一个数字，而这次我们存储更加复杂的数据。以 github user API 为例( <a href="http://link.zhihu.com/?target=http%3A//api.github.com/users/codefalling" class=" external" target="_blank" rel="nofollow noreferrer"><span class="invisible">http://</span><span class="visible">api.github.com/users/co</span><span class="invisible">defalling</span><span class="ellipsis"></span><i class="icon-external"></i></a> )，我们来写一段代码来获取指定用户头像。</p><h3>初始化 store</h3><p>我们将初始化 store 的地方改为：</p><div class="highlight"><pre><code class="language-js"><span></span><span class="kr">const</span> <span class="nx">store</span> <span class="o">=</span> <span class="nx">createStoreWithMiddleware</span><span class="p">(</span><span class="nx">reducer</span><span class="p">,</span> <span class="p">{</span>  
  <span class="nx">username</span><span class="o">:</span> <span class="kc">null</span><span class="p">,</span>

  <span class="nx">info</span><span class="o">:</span> <span class="p">{</span>
    <span class="nx">fetching</span><span class="o">:</span> <span class="kc">null</span><span class="p">,</span>
   <span class="nx">fetched</span><span class="o">:</span> <span class="kc">null</span><span class="p">,</span>
  <span class="p">}</span>
<span class="p">},</span>
<span class="nx">applyMiddleware</span><span class="p">(</span><span class="nx">logger</span><span class="p">))</span>  
</code></pre></div><h3>异步 action</h3><p>看起来我们只需要一个获取头像的 action，但其实我们应该还需要一个获取成功的 action，因为获取头像不会马上得到数据，而请求返回后应该更新 state。</p><p>在这里我们使用 redux-thunk, (因为 cdn 上找不到 redux-promise 之类的。。)。</p><p>同样的，在左侧的 External Resources 中引入<a href="http://link.zhihu.com/?target=http%3A//cdnjs.cloudflare.com/ajax/libs/redux-thunk/2.1.0/redux-thunk.min.js" class=" external" target="_blank" rel="nofollow noreferrer"><span class="invisible">http://</span><span class="visible">cdnjs.cloudflare.com/aj</span><span class="invisible">ax/libs/redux-thunk/2.1.0/redux-thunk.min.js</span><span class="ellipsis"></span><i class="icon-external"></i></a> 。</p><p>然后只要将 applyMiddleware(logger) 改为 applyMiddleware(logger, ReduxThunk.default)。</p><p>然后我们就能写出类似</p><div class="highlight"><pre><code class="language-js"><span></span><span class="nx">store</span><span class="p">.</span><span class="nx">dispatch</span><span class="p">(</span><span class="nx">dispatch</span> <span class="o">=&gt;</span> <span class="p">{</span>  
  <span class="nx">dispatch</span><span class="p">({</span> <span class="nx">type</span><span class="o">:</span> <span class="s1">'FETCH_START'</span> <span class="p">})</span>
  <span class="nx">fetch</span><span class="p">(</span><span class="s1">'http://api.github.com/users/codefalling'</span><span class="p">).</span><span class="nx">then</span><span class="p">(</span><span class="nx">res</span> <span class="o">=&gt;</span> <span class="p">{</span>
    <span class="k">return</span> <span class="nx">res</span><span class="p">.</span><span class="nx">text</span><span class="p">()</span>
  <span class="p">})</span>
  <span class="p">.</span><span class="nx">then</span><span class="p">(</span><span class="nx">data</span> <span class="o">=&gt;</span> <span class="p">{</span>
    <span class="kr">const</span> <span class="nx">obj</span> <span class="o">=</span> <span class="nx">JSON</span><span class="p">.</span><span class="nx">parse</span><span class="p">(</span><span class="nx">data</span><span class="p">)</span>
    <span class="kr">const</span> <span class="nx">avatarUrl</span> <span class="o">=</span> <span class="nx">obj</span><span class="p">[</span><span class="s1">'avatar_url'</span><span class="p">]</span>
    <span class="kr">const</span> <span class="nx">blog</span> <span class="o">=</span> <span class="nx">obj</span><span class="p">.</span><span class="nx">blog</span>
    <span class="nx">dispatch</span><span class="p">({</span> <span class="nx">type</span><span class="o">:</span> <span class="s1">'FETCH_END'</span><span class="p">,</span> <span class="nx">payload</span><span class="o">:</span> <span class="p">{</span> <span class="nx">avatarUrl</span><span class="p">,</span> <span class="nx">blog</span> <span class="p">}</span> <span class="p">})</span>
  <span class="p">})</span>
<span class="p">})</span>
</code></pre></div><p>然后会先触发 FETCH<em>START，完成后带着数据触发 FETCH</em>END。</p><p>很容易可以写出对应的 reducer，FETCH<em>START 时把 fetching 设为 true，FETCH</em>END 时设置 avatarUrl 并且将 fetched 设为 true，fetching 设为 false.</p><div class="highlight"><pre><code class="language-js"><span></span><span class="kr">const</span> <span class="nx">reducer</span> <span class="o">=</span> <span class="p">(</span><span class="nx">state</span><span class="p">,</span> <span class="nx">action</span><span class="p">)</span> <span class="o">=&gt;</span> <span class="p">{</span>  
  <span class="k">switch</span> <span class="p">(</span><span class="nx">action</span><span class="p">.</span><span class="nx">type</span><span class="p">)</span> <span class="p">{</span>
    <span class="k">case</span> <span class="s2">"FETCH_START"</span><span class="o">:</span>
      <span class="k">return</span> <span class="p">{</span>
        <span class="nx">fetching</span><span class="o">:</span> <span class="kc">true</span><span class="p">,</span>
      <span class="p">}</span>
    <span class="k">case</span> <span class="s2">"FETCH_END"</span><span class="o">:</span>
      <span class="k">return</span> <span class="p">{</span>
        <span class="nx">fetching</span><span class="o">:</span> <span class="kc">false</span><span class="p">,</span>
        <span class="nx">fetched</span><span class="o">:</span> <span class="kc">true</span><span class="p">,</span>
        <span class="nx">info</span><span class="o">:</span> <span class="p">{</span>
          <span class="nx">avatarUrl</span><span class="o">:</span> <span class="nx">action</span><span class="p">.</span><span class="nx">payload</span><span class="p">.</span><span class="nx">avatarUrl</span><span class="p">,</span>
          <span class="nx">blog</span><span class="o">:</span> <span class="nx">action</span><span class="p">.</span><span class="nx">payload</span><span class="p">.</span><span class="nx">avatarUrl</span><span class="p">,</span>
        <span class="p">},</span>
      <span class="p">}</span>
  <span class="p">}</span>
<span class="p">}</span>
</code></pre></div><h2>拆分 reducer</h2><p>前面曾经提到，redux 只有一个 store，当应用变得越来越复杂时，reducer 和 store 中的数据都越来越多。而 reducer 可能并不关心和自己无关的 state，把 reducer 全部写在一个大 switch case 中也不是个好主意，所以我们要将 reducer 拆分开。redux 提供一个函数，combineReducers，用于合并多个 reducer。</p><p>以上面的代码为例，假设我们有一个和其没有关系的其他 reducer，我们可以写成：</p><div class="highlight"><pre><code class="language-js"><span></span><span class="kr">const</span> <span class="p">{</span> <span class="nx">createStore</span><span class="p">,</span> <span class="nx">applyMiddleware</span><span class="p">,</span> <span class="nx">combineReducers</span> <span class="p">}</span> <span class="o">=</span> <span class="nx">Redux</span>

<span class="kr">const</span> <span class="nx">fetchReducer</span> <span class="o">=</span> <span class="p">(</span><span class="nx">state</span> <span class="o">=</span> <span class="p">{},</span> <span class="nx">action</span><span class="p">)</span> <span class="o">=&gt;</span> <span class="p">{</span>  
  <span class="k">switch</span> <span class="p">(</span><span class="nx">action</span><span class="p">.</span><span class="nx">type</span><span class="p">)</span> <span class="p">{</span>
    <span class="k">case</span> <span class="s2">"FETCH_START"</span><span class="o">:</span>
      <span class="k">return</span> <span class="p">{</span>
        <span class="p">...</span><span class="nx">state</span><span class="p">,</span>
        <span class="nx">fetching</span><span class="o">:</span> <span class="kc">true</span><span class="p">,</span>
      <span class="p">}</span>
    <span class="k">case</span> <span class="s2">"FETCH_END"</span><span class="o">:</span>
      <span class="k">return</span> <span class="p">{</span>
        <span class="p">...</span><span class="nx">state</span><span class="p">,</span>
        <span class="nx">fetching</span><span class="o">:</span> <span class="kc">false</span><span class="p">,</span>
        <span class="nx">fetched</span><span class="o">:</span> <span class="kc">true</span><span class="p">,</span>
        <span class="nx">info</span><span class="o">:</span> <span class="p">{</span>
          <span class="nx">avatarUrl</span><span class="o">:</span> <span class="nx">action</span><span class="p">.</span><span class="nx">payload</span><span class="p">.</span><span class="nx">avatarUrl</span><span class="p">,</span>
          <span class="nx">blog</span><span class="o">:</span> <span class="nx">action</span><span class="p">.</span><span class="nx">payload</span><span class="p">.</span><span class="nx">avatarUrl</span><span class="p">,</span>
        <span class="p">},</span>
      <span class="p">}</span>
  <span class="p">}</span>
  <span class="k">return</span> <span class="nx">state</span>
<span class="p">}</span>

<span class="kr">const</span> <span class="nx">helloReducer</span> <span class="o">=</span> <span class="p">(</span><span class="nx">state</span> <span class="o">=</span> <span class="p">{},</span> <span class="nx">action</span><span class="p">)</span> <span class="o">=&gt;</span> <span class="p">{</span>  
  <span class="k">if</span> <span class="p">(</span><span class="nx">action</span><span class="p">.</span><span class="nx">type</span> <span class="o">===</span> <span class="s1">'HELLO'</span><span class="p">)</span> <span class="p">{</span>
      <span class="nx">state</span> <span class="o">=</span> <span class="nx">action</span><span class="p">.</span><span class="nx">payload</span>
  <span class="p">}</span>
  <span class="k">return</span> <span class="nx">state</span>
<span class="p">}</span>

<span class="kr">const</span> <span class="nx">reducer</span> <span class="o">=</span> <span class="nx">combineReducers</span><span class="p">({</span>  
  <span class="nx">fetch</span><span class="o">:</span> <span class="nx">fetchReducer</span><span class="p">,</span>
  <span class="nx">hello</span><span class="o">:</span> <span class="nx">helloReducer</span><span class="p">,</span>
<span class="p">})</span>

<span class="kr">const</span> <span class="nx">logger</span> <span class="o">=</span> <span class="nx">store</span> <span class="o">=&gt;</span> <span class="nx">next</span> <span class="o">=&gt;</span> <span class="nx">action</span> <span class="o">=&gt;</span> <span class="p">{</span>  
  <span class="nx">console</span><span class="p">.</span><span class="nx">log</span><span class="p">(</span><span class="s1">'dispatching'</span><span class="p">,</span> <span class="nx">action</span><span class="p">)</span>
  <span class="kd">let</span> <span class="nx">result</span> <span class="o">=</span> <span class="nx">next</span><span class="p">(</span><span class="nx">action</span><span class="p">)</span>
  <span class="nx">console</span><span class="p">.</span><span class="nx">log</span><span class="p">(</span><span class="s1">'next state'</span><span class="p">,</span> <span class="nx">store</span><span class="p">.</span><span class="nx">getState</span><span class="p">())</span>
  <span class="k">return</span> <span class="nx">result</span>
<span class="p">}</span>

<span class="kr">const</span> <span class="nx">store</span> <span class="o">=</span> <span class="nx">createStore</span><span class="p">(</span><span class="nx">reducer</span><span class="p">,</span> <span class="p">{},</span> <span class="nx">applyMiddleware</span><span class="p">(</span><span class="nx">logger</span><span class="p">,</span> <span class="nx">ReduxThunk</span><span class="p">.</span><span class="k">default</span><span class="p">))</span>

<span class="nx">store</span><span class="p">.</span><span class="nx">dispatch</span><span class="p">(</span><span class="nx">dispatch</span> <span class="o">=&gt;</span> <span class="p">{</span>  
  <span class="nx">dispatch</span><span class="p">({</span> <span class="nx">type</span><span class="o">:</span> <span class="s1">'FETCH_START'</span> <span class="p">})</span>
  <span class="nx">fetch</span><span class="p">(</span><span class="s1">'http://api.github.com/users/codefalling'</span><span class="p">).</span><span class="nx">then</span><span class="p">(</span><span class="nx">res</span> <span class="o">=&gt;</span> <span class="p">{</span>
    <span class="k">return</span> <span class="nx">res</span><span class="p">.</span><span class="nx">text</span><span class="p">()</span>
  <span class="p">})</span>
  <span class="p">.</span><span class="nx">then</span><span class="p">(</span><span class="nx">data</span> <span class="o">=&gt;</span> <span class="p">{</span>
    <span class="kr">const</span> <span class="nx">avatarUrl</span> <span class="o">=</span> <span class="nx">JSON</span><span class="p">.</span><span class="nx">parse</span><span class="p">(</span><span class="nx">data</span><span class="p">)[</span><span class="s1">'avatar_url'</span><span class="p">]</span>
      <span class="nx">dispatch</span><span class="p">({</span> <span class="nx">type</span><span class="o">:</span> <span class="s1">'FETCH_END'</span><span class="p">,</span> <span class="nx">payload</span><span class="o">:</span> <span class="nx">avatarUrl</span> <span class="p">})</span>
  <span class="p">})</span>
<span class="p">})</span>
</code></pre></div><p>初始化不再在 store 中完成，而是直接写在缺省参数里。拆分开的 reducer 不能返回 undefined，如果什么都没发生，就原样返回即可。</p><p>我们可以看到，多个 reducer 被拆分开，各自独立，state 也不会互相影响。</p><h2>更多</h2><p>到这里介绍完了 redux 中比较重要的概念，本文为了简单和易于理解没有引入 react，先搞清楚 redux 本身的工作方式，避免陷入茫茫多的细节和概念。将会在未来的文章中介绍 react 和 redux 共同工作的方式。</p><h2><b>其他</b></h2><p>原文地址: <a href="http://link.zhihu.com/?target=http%3A//codefalling.com/2016/10/05/learn-redux-from-zero/" class=" external" target="_blank" rel="nofollow noreferrer"><span class="invisible">http://</span><span class="visible">codefalling.com/2016/10</span><span class="invisible">/05/learn-redux-from-zero/</span><span class="ellipsis"></span><i class="icon-external"></i></a></p><p>感觉自己已经葛优躺了好几个礼拜。。几乎是个废前端了。。</p>