## FUNCTION ARGUMENTS

### Parameters and Arguments

<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Python's functions offer us a very expressive syntax. We're going to look into some of the finer details of how functions in Python work and some techniques we can use to be more intuitive while writing and calling functions.</p>
<p>First, let's consider some definitions:
A <em>parameter</em> is a variable in the definition of a function.
An <em>argument</em> is the value being passed into a function call.
A <em>function definition</em> begins with <code>def</code> and contains the entire following indented block.
And <em>function calls</em> are the places a function is invoked, with parentheses, after its definition</p>
<p>Let's see this in a block of code:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-comment"># The "def" keyword is the start of a function definition</span>
<span class="cm-keyword">def</span> <span class="cm-def">function_name</span>(<span class="cm-variable">parameter1</span>, <span class="cm-variable">parameter2</span>):
  <span class="cm-comment"># The placeholder variables used inside a function definition are called parameters</span>
  <span class="cm-builtin">print</span>(<span class="cm-variable">parameter1</span>)
  <span class="cm-keyword">return</span> <span class="cm-variable">parameter2</span>
<span class="cm-comment"># The outdent signals the end of the function definition</span>

<span class="cm-comment"># "Arguments" are the values passed into a function call</span>
<span class="cm-variable">argument1</span> <span class="cm-operator">=</span> <span class="cm-string">"argument 1"</span>
<span class="cm-variable">argument2</span> <span class="cm-operator">=</span> <span class="cm-string">"argument 2"</span>

<span class="cm-comment"># A function call uses the functions name with a pair of parentheses</span>
<span class="cm-comment"># and can return a value</span>
<span class="cm-variable">return_val</span> <span class="cm-operator">=</span> <span class="cm-variable">function_name</span>(<span class="cm-variable">argument1</span>, <span class="cm-variable">argument2</span>)</div></span></pre>
<p>In the above code we defined the function <code>function_name</code> that takes two parameters, <code>parameter1</code> and <code>parameter2</code>. We then create two variables with the values <code>"argument 1"</code> and <code>"argument 2"</code> and proceed to call <code>function_name</code> with the two arguments.</p>
<p>Some of this terminology can be used inconsistently between schools, people, and businesses. Some people don't differentiate between "parameter" and "argument" when speaking. It's useful here because we're going to be looking at a lot of behavior that looks very similar in a function definition and a function call, but will be subtly different. But the distinction is sometimes unnecessary, so don't get too hung up if something is called a "parameter" that should be an "argument" or vice versa.</p>
</div>

###### TASK
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>In <strong>script.py</strong> call the function <code>play_record</code> with the argument <code>next_album</code>. </p>
<p>What's the name of the parameter that <code>play_record</code> takes?</p>
</div>

```python
from record_library import place_record, rotate_record, drop_needle

def play_record(album):
  place_record(album)
  rotate_record(album)
  drop_needle(album)

next_album = "Blondie / Parallel Lines"
play_record(next_album)
```

### None: It's Nothing!
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>How do you define a variable that you can't assign a value to yet? You use <code>None</code>. </p>
<p><code>None</code> is a special value in Python. It is unique (there can't be two different <code>None</code>s) and immutable (you can't update <code>None</code> or assign new attributes to it).</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-variable">none_var</span> <span class="cm-operator">=</span> <span class="cm-keyword">None</span>
<span class="cm-keyword">if</span> <span class="cm-variable">none_var</span>:
  <span class="cm-builtin">print</span>(<span class="cm-string">"Hello!"</span>)
<span class="cm-keyword">else</span>:
  <span class="cm-builtin">print</span>(<span class="cm-string">"Goodbye"</span>)

<span class="cm-comment"># Prints "Goodbye"</span></div></span></pre>
<p><code>None</code> is falsy, meaning that it evaluates to <code>False</code> in an <code>if</code> statement, which is why the above code prints "Goodbye". <code>None</code> is also <em>unique</em>, which means that you can test if something is <code>None</code> using the <code>is</code> keyword.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-comment"># first we define session_id as None</span>
<span class="cm-variable">session_id</span> <span class="cm-operator">=</span> <span class="cm-keyword">None</span>

<span class="cm-keyword">if</span> <span class="cm-variable">session_id</span> <span class="cm-keyword">is</span> <span class="cm-keyword">None</span>:
  <span class="cm-builtin">print</span>(<span class="cm-string">"session ID is None!"</span>)
  <span class="cm-comment"># this prints out "session ID is None!"</span>

<span class="cm-comment"># we can assign something to session_id</span>
<span class="cm-keyword">if</span> <span class="cm-variable">active_session</span>:
  <span class="cm-variable">session_id</span> <span class="cm-operator">=</span> <span class="cm-variable">active_session</span>.<span class="cm-property">id</span>

<span class="cm-comment"># but if there's no active_session, we don't send sensitive data</span>
<span class="cm-keyword">if</span> <span class="cm-variable">session_id</span> <span class="cm-keyword">is</span> <span class="cm-keyword">not</span> <span class="cm-keyword">None</span>:
  <span class="cm-variable">send_sensitive_data</span>(<span class="cm-variable">session_id</span>)</div></span></pre>
<p>Above we initialize our <code>session_id</code> to <code>None</code>, then set our <code>session_id</code> if there is an active session. Since <code>session_id</code> could either be <code>None</code> we check if <code>session_id</code> is <code>None</code> before sending our sensitive data.</p>
</div>

###### TASK
<p>Grab a new review using <code>get_next_review()</code>. Save the results into a variable called <code>review</code>.</p>

```python

```
