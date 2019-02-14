## Classes
### Types
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Python equips us with many different ways to store data. A <code>float</code> is a different kind of number from an <code>int</code>, and we store different data in a <code>list</code> than we do in a <code>dict</code>. These are known as different <em>types</em>. We can check the type of a Python variable using the <code>type()</code> function.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-variable">a_string</span> <span class="cm-operator">=</span> <span class="cm-string">"Cool String"</span>
<span class="cm-variable">an_int</span> <span class="cm-operator">=</span> <span class="cm-number">12</span>

<span class="cm-builtin">print</span>(<span class="cm-builtin">type</span>(<span class="cm-variable">a_string</span>))
<span class="cm-comment"># prints "&lt;class 'str'&gt;"</span>

<span class="cm-builtin">print</span>(<span class="cm-builtin">type</span>(<span class="cm-variable">an_int</span>))
<span class="cm-comment"># prints "&lt;class 'int'&gt;"</span></div></span></pre>
<p>Above, we defined two variables, and checked the <code>type</code> of these two variables. A variable's type determines what you can do with it and how you can use it. You can't <code>.get()</code> something from an integer, just as you can't add two dictionaries together using <code>+</code>. This is because those operations are defined at the <code>type</code> level.</p>
</div>

###### TASK

* <p>Call <code>type()</code> on the integer <code>5</code> and print the results.</p>

* <p>Define a dictionary <code>my_dict</code>.</p>

* <p>Print out the <code>type()</code> of <code>my_dict</code>.</p>

* <p>Define a list called <code>my_list</code>.</p>

* <p>Print out the <code>type()</code> of <code>my_list</code>.</p>

```python 
<p>Print out the <code>type()</code> of <code>my_list</code>.</p>
```

### Class
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>A <em>class</em> is a template for a data type. It describes the kinds of information that class will hold and how a programmer will interact with that data. Define a class using the <code>class</code> keyword. &lt;a href="<a href="https://www.python.org/dev/peps/pep-0008/#class-names&quot;">https://www.python.org/dev/peps/pep-0008/#class-names"</a> target="_blank", rel="noopener noreferrer"&gt;PEP 8 Style Guide for Python Code  recommends capitalizing the names of classes to make them easier to identify.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">class</span> <span class="cm-def">CoolClass</span>:
  <span class="cm-keyword">pass</span></div></span></pre>
<p>In the above example we created a class and named it <code>CoolClass</code>. We used the <code>pass</code> keyword in Python to indicate that the body of the class was intentionally left blank so we don't cause an <code>IndentationError</code>. We’ll learn about all the things we can put in the body of a class in the next few exercises.</p>
</div>

###### TASK
<p>Define an empty class called <code>Facade</code>. We'll chip away at it soon!</p>
