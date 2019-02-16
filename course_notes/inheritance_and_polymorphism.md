##  INHERITANCE AND POLYMORPHISM

### Inheritance 

<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Classes are designed to allow for more code reuse, but what if we need a class that looks a lot like a class we already have? If the bulk of a class's definition is useful, but we have a new use case that is distinct from how the original class was used, we can <em>inherit</em> from the original class. Think of inheritance as a remix — it sounds a lot like the original, but there's something... different about it.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">class</span> <span class="cm-def">User</span>:
  <span class="cm-variable">is_admin</span> <span class="cm-operator">=</span> <span class="cm-keyword">False</span>
  <span class="cm-keyword">def</span> <span class="cm-def">__init__</span>(<span class="cm-variable-2">self</span>, <span class="cm-variable">username</span>)
    <span class="cm-variable-2">self</span>.<span class="cm-property">username</span> <span class="cm-operator">=</span> <span class="cm-variable">username</span>

<span class="cm-keyword">class</span> <span class="cm-def">Admin</span>(<span class="cm-variable">User</span>):
  <span class="cm-variable">is_admin</span> <span class="cm-operator">=</span> <span class="cm-keyword">True</span></div></span></pre>
<p>Above we defined <code>User</code> as our <em>base class</em>. We want to create a new class that inherits from it, so we created the <em>subclass</em> <code>Admin</code>. In the above example, <code>Admin</code> has the same constructor as <code>User</code>. Only the class variable <code>is_admin</code> is set differently between the two.</p>
<p>Sometimes a base class is called a <em>parent class</em>. In these terms, the class inheriting from it, the subclass, is also referred to as a <em>child class</em>.</p>
</div>

###### TASK
<p>In <strong>script.py</strong> we've already defined the class <code>Bin</code>. Create a subclass of <code>Bin</code> called <code>RecyclingBin</code>.</p>

```python
class Bin:
  pass

class RecyclingBin(Bin):
  pass
```

### Exceptions
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>There's one very important family of class definitions built in to the Python language. An <em>Exception</em> is a class that inherits from Python's <code>Exception</code> class.</p>
<p>We can validate this ourselves using the <code>issubclass()</code> function. <code>issubclass()</code> is a Python built-in function that takes two parameters. <code>issubclass()</code> returns <code>True</code> if the first argument is a subclass of the second argument. It returns <code>False</code> if the first class is not a subclass of the second. <code>issubclass()</code> raises a <code>TypeError</code> if either argument passed in is not a class.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-builtin">issubclass</span>(<span class="cm-variable">ZeroDivisionError</span>, <span class="cm-variable">Exception</span>)
<span class="cm-comment"># Returns True</span></div></span></pre>
<p>Above, we checked whether <code>ZeroDivisionError</code>, the exception raised when attempting division by zero, is a subclass of <code>Exception</code>. It is, so <code>issubclass</code> returns <code>True</code>.</p>
<p>Why is it beneficial for exceptions to inherit from one another? Let's consider an example where we create our own exceptions. What if we were creating software that tracks our kitchen appliances? We would be able to design a suite of exceptions for that need:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">class</span> <span class="cm-def">KitchenException</span>(<span class="cm-variable">Exception</span>):
  <span class="cm-string">"""</span>
<span class="cm-string">  Exception that gets thrown when a kitchen appliance isn't working</span>
<span class="cm-string">  """</span>

<span class="cm-keyword">class</span> <span class="cm-def">MicrowaveException</span>(<span class="cm-variable">KitchenException</span>):
  <span class="cm-string">"""</span>
<span class="cm-string">  Exception for when the microwave stops working</span>
<span class="cm-string">  """</span>

<span class="cm-keyword">class</span> <span class="cm-def">RefrigeratorException</span>(<span class="cm-variable">KitchenException</span>):
  <span class="cm-string">"""</span>
<span class="cm-string">  Exception for when the refrigerator stops working</span>
<span class="cm-string">  """</span></div></span></pre>
<p>In this code, we define three exceptions. First, we define a <code>KitchenException</code> that acts as the parent to our other, specific kitchen appliance exceptions. <code>KitchenException</code> subclasses <code>Exception</code>, so it behaves in the same way that regular <code>Exception</code>s do. Afterward we define <code>MicrowaveException</code> and <code>RefrigeratorException</code> as subclasses.</p>
<p>Since our exceptions are subclassed in this way, we can catch any of <code>KitchenException</code>'s subclasses by catching <code>KitchenException</code>. For example:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">def</span> <span class="cm-def">get_food_from_fridge</span>():
  <span class="cm-keyword">if</span> <span class="cm-variable">refrigerator</span>.<span class="cm-property">cooling</span> <span class="cm-operator">==</span> <span class="cm-keyword">False</span>:
    <span class="cm-keyword">raise</span> <span class="cm-variable">RefrigeratorException</span>
  <span class="cm-keyword">else</span>:
    <span class="cm-keyword">return</span> <span class="cm-variable">food</span>

<span class="cm-keyword">def</span> <span class="cm-def">heat_food</span>(<span class="cm-variable">food</span>):
  <span class="cm-keyword">if</span> <span class="cm-variable">microwave</span>.<span class="cm-property">working</span> <span class="cm-operator">==</span> <span class="cm-keyword">False</span>:
    <span class="cm-keyword">raise</span> <span class="cm-variable">MicrowaveException</span>
  <span class="cm-keyword">else</span>:
    <span class="cm-variable">microwave</span>.<span class="cm-property">cook</span>(<span class="cm-variable">food</span>)
    <span class="cm-keyword">return</span> <span class="cm-variable">food</span>

<span class="cm-keyword">try</span>:
  <span class="cm-variable">food</span> <span class="cm-operator">=</span> <span class="cm-variable">get_food_from_fridge</span>()
  <span class="cm-variable">food</span> <span class="cm-operator">=</span> <span class="cm-variable">heat_food</span>(<span class="cm-variable">food</span>)
<span class="cm-keyword">except</span> <span class="cm-variable">KitchenException</span>:
  <span class="cm-variable">food</span> <span class="cm-operator">=</span> <span class="cm-variable">order_takeout</span>()</div></span></pre>
<p>In the above example, we attempt to retrieve food from the fridge and heat it in the microwave. If either <code>RefrigeratorException</code> or <code>MicrowaveException</code> is raised, we opt to order takeout instead. We catch both <code>RefrigeratorException</code> and <code>MicrowaveException</code> in our try/except block because both are subclasses of <code>KitchenException</code>.</p>
<p>Explore Python's exception hierarchy in the <a href="https://docs.python.org/3/library/exceptions.html#exception-hierarchy" target="_blank">Python documentation</a>!</p>
</div>


###### TASK
* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>In <strong>script.py</strong> we've defined a <code>CandleShop</code> class for our new candle shop that we've named <em>Here's a Hot Tip: Buy Drip Candles</em>. We want to define our own exceptions for when we run out of candles to sell.</p>
<p>Define your own exception called <code>OutOfStock</code> that inherits from the <code>Exception</code> class.</p>
</div>

* 



```python

```
