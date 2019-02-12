## Python Functions
### Introduction
<div class="theme__22QeW-d-YRjfwg7z9oiZH_"><p>This lesson will help you review Python functions by providing some challenge exercises.</p>
<p>As a refresher, function syntax looks like this:</p>
<pre><code class="lang-py"><span language="py" class="CodeBlock__3-kebd7REMI5aXkez6K-B wrap__yxnEyEmMpigk6-3_Wvbzo defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined" data-reactroot=""><div class="CodeMirror"><span class="cm-keyword">def</span> <span class="cm-def">some_function</span>(<span class="cm-variable">some_input1</span>,<!-- --> <span class="cm-variable">some_input2</span>)<!-- -->:<!-- -->
<!-- -->  <span class="cm-variable">…</span> <span class="cm-variable">do</span> <span class="cm-variable">something</span> <span class="cm-keyword">with</span> <span class="cm-variable">the</span> <span class="cm-variable">inputs</span> <span class="cm-variable">…</span>
<!-- -->  <span class="cm-keyword">return</span> <span class="cm-variable">output</span></div></span>
</code></pre>
<p>For example, a function that takes in a number and returns that number multiplied by 4 would look like:</p>
<pre><code class="lang-py"><span language="py" class="CodeBlock__3-kebd7REMI5aXkez6K-B wrap__yxnEyEmMpigk6-3_Wvbzo defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined" data-reactroot=""><div class="CodeMirror"><span class="cm-keyword">def</span> <span class="cm-def">mult_by_four</span>(<span class="cm-variable">number</span>)<!-- -->:<!-- -->
<!-- -->  <span class="cm-variable">multiplied</span> <span class="cm-operator">=</span> <span class="cm-variable">number</span> <span class="cm-operator">*</span> <span class="cm-number">4</span>
<!-- -->  <span class="cm-keyword">return</span> <span class="cm-variable">multiplied</span></div></span>
</code></pre>
<p>And this would produce output like:</p>
<pre><code><span class="CodeBlock__3-kebd7REMI5aXkez6K-B wrap__yxnEyEmMpigk6-3_Wvbzo defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined" data-reactroot=""><div class="CodeMirror">&gt;&gt;&gt; mult_by_four(10)<!-- -->
<!-- -->40<!-- -->
<!-- -->&gt;&gt;&gt; mult_by_four(0)<!-- -->
<!-- -->0<!-- -->
<!-- -->&gt;&gt;&gt; mult_by_four(-1)<!-- -->
<!-- -->-4</div></span>
</code></pre></div>

###### TASK
<div class="theme__22QeW-d-YRjfwg7z9oiZH_"><p>Write a function named <code>average()</code> that has two parameters named <code>num1</code> and <code>num2</code>. </p>
<p>The function should return the average of these two numbers.</p>
</div>

```python
def average(num1, num2):
  return (num1 + num2)/2
```

### Tenth Power
