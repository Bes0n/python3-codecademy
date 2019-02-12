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
tenth_power()

###### TASK
<div class="theme__22QeW-d-YRjfwg7z9oiZH_"><p>Write a function named <code>tenth_power()</code> that has one parameter named <code>num</code>. </p>
<p>The function should return <code>num</code> raised to the 10th power.</p>
</div>

```python
def tenth_power(num):
  return num ** 10
  
```

### Bond 
introduction()

###### TASK
<div class="theme__22QeW-d-YRjfwg7z9oiZH_"><p>Write a function named <code>introduction()</code> that has two parameters named <code>first_name</code> and <code>last_name</code>. </p>
<p>The function should return the <code>last_name</code>, followed by a comma, a space, <code>first_name</code> another space, and finally <code>last_name</code>. </p>
</div>

```python 
def introduction(first_name, last_name):
  return "%s, %s %s" % (last_name, first_name, last_name)
```

### Square Root
square_root()

###### TASK
<div class="theme__22QeW-d-YRjfwg7z9oiZH_"><p>Write a function named <code>square_root()</code> that has one parameter named <code>num</code>. </p>
<p>Use exponents (<code>**</code>) to return the square root of <code>num</code>.</p>
</div>

```python 
def square_root(num):
  return num ** 0.5
```

### Tip
tip()

###### TASK
<div class="theme__22QeW-d-YRjfwg7z9oiZH_"><p>Create a function called <code>tip()</code> that has two parameters named <code>total</code> and <code>percentage</code>. </p>
<p>This function should return the amount you should tip given a total and the percentage you want to tip.</p>
</div>

```python
def tip(total, percentage):
  return total * percentage / 100
```

### Win Percentage
win_percentage()

###### TASK
<div class="theme__22QeW-d-YRjfwg7z9oiZH_"><p>Create a function called <code>win_percentage()</code> that takes two parameters named <code>wins</code> and <code>losses</code>. </p>
<p>This function should return out the total percentage of games won by a team based on these two numbers.</p>
</div>

```python 
# Write your win_percentage function here:
def win_percentage(wins,losses):
  total = wins + losses
  return (100 * wins) / total
# Uncomment these function calls to test your win_percentage function:
print(win_percentage(5, 5))
# should print 50
print(win_percentage(10, 0))
# should print 100
```

### First Three Multiples
first_three_multiples()

###### TASK
<div class="theme__22QeW-d-YRjfwg7z9oiZH_"><p>Write a function named <code>first_three_multiples()</code> that has one parameter named <code>num</code>. </p>
<p>This function should print the first three multiples of <code>num</code>. Then, it should return the third multiple.</p>
<p>For example, <code>first_three_multiples(7)</code> should print <code>7</code>, <code>14</code>, and <code>21</code> on three different lines, and return <code>21</code>.</p>
</div>

```python 
def first_three_multiples(num):
  for i in range(1,4):
    print(num * i)
  return num * i 

first_three_multiples(7) 
```

