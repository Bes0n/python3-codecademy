## STRING METHODS
### Introduction
<div class="theme__22QeW-d-YRjfwg7z9oiZH_"><p>This lesson will help you review Python functions by providing some challenge exercises involving Strings.</p>
<p>As a refresher, function syntax looks like this:</p>
<pre><code class="lang-py"><span language="py" class="CodeBlock__3-kebd7REMI5aXkez6K-B wrap__yxnEyEmMpigk6-3_Wvbzo defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined" data-reactroot=""><div class="CodeMirror"><span class="cm-keyword">def</span> <span class="cm-def">some_function</span>(<span class="cm-variable">some_input1</span>,<!-- --> <span class="cm-variable">some_input2</span>)<!-- -->:<!-- -->
<!-- -->  <span class="cm-variable">…</span> <span class="cm-variable">do</span> <span class="cm-variable">something</span> <span class="cm-keyword">with</span> <span class="cm-variable">the</span> <span class="cm-variable">inputs</span> <span class="cm-variable">…</span>
<!-- -->  <span class="cm-keyword">return</span> <span class="cm-variable">output</span></div></span>
</code></pre>
<p>For example, a function that finds the difference in length between two Strings would look like this:</p>
<pre><code class="lang-py"><span language="py" class="CodeBlock__3-kebd7REMI5aXkez6K-B wrap__yxnEyEmMpigk6-3_Wvbzo defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined" data-reactroot=""><div class="CodeMirror"><span class="cm-keyword">def</span> <span class="cm-def">lengthDiff</span>(<span class="cm-variable">str1</span>,<!-- --> <span class="cm-variable">str2</span>)<!-- -->:<!-- -->
<!-- -->  <span class="cm-keyword">return</span> <span class="cm-builtin">len</span>(<span class="cm-variable">str1</span>)<!-- --> <span class="cm-operator">-</span> <span class="cm-builtin">len</span>(<span class="cm-variable">str2</span>)</div></span>
</code></pre>
<p>And this would produce output like:</p>
<pre><code><span class="CodeBlock__3-kebd7REMI5aXkez6K-B wrap__yxnEyEmMpigk6-3_Wvbzo defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined" data-reactroot=""><div class="CodeMirror">&gt;&gt;&gt; lengthDiff("Python", "rocks")<!-- -->
<!-- -->1<!-- -->
<!-- -->&gt;&gt;&gt; lengthDiff("Marco", "Polo")<!-- -->
<!-- -->1<!-- -->
<!-- -->&gt;&gt;&gt; lengthDiff("Kevin", "Durant")<!-- -->
<!-- -->-1</div></span>
</code></pre><p>When you're ready to do this series of short function challenges, continue on to the rest of the lesson!</p>
</div>

### Count Letters
unique_english_letters(word)

###### TASK
<div class="theme__22QeW-d-YRjfwg7z9oiZH_"><p>Write a function called <code>unique_english_letters</code> that takes the string <code>word</code> as a parameter. The function should return the total number of unique letters in the string. Uppercase and lowercase letters should be counted as different letters.</p>
<p>We've given you a list of every uppercase and lower case letter in the English alphabet. It will be helpful to include that list in your function.</p>
</div>

```python
#my solution:
def unique_english_letters(word):
  unique_list = []
  for char in word:
    if char not in unique_list:
      unique_list.append(char)
  return len(unique_list)
  
#codecademy:
def unique_english_letters(word):
  uniques = 0
  for letter in letters:
    if letter in word:
      uniques += 1
  return uniques

```

### Count X
count_char_x()

###### TASK
<p>Write a function named <code>count_char_x</code> that takes a string named <code>word</code> and a single character named <code>x</code> as parameters. The function should return the number of times <code>x</code> appears in <code>word</code>.</p>

```python
def count_char_x(word, x):
  count = 0 
  for char in word:
    if x == char:
      count += 1
  return count
```

### Count Multi X
count_multi_char_x()

###### TASK
<div class="theme__22QeW-d-YRjfwg7z9oiZH_"><p>Wire a function named <code>count_multi_char_x</code> that takes a string named <code>word</code> and a string named <code>x</code>. This function should do the same thing as the <code>count_char_x</code> function you just wrote - it should return the number of times <code>x</code> appears in <code>word</code>. However, this time, make sure your function works when <code>x</code> is multiple characters long.</p>
<p>For example, <code>count_multi_char_x("Mississippi", "iss")</code> should return <code>2</code></p>
</div>

```python
# Write your count_multi_char_x function here:
def count_multi_char_x(word, x):
  count = 0
  for item in word.split(x):
    count += 1
  return count - 1

# Uncomment these function calls to test your  function:
print(count_multi_char_x("mississippi", "iss"))
# should print 2
print(count_multi_char_x("apple", "pp"))
# should print 1
```

### Substring Between
substring_between_letters()

###### TASK
<div class="theme__22QeW-d-YRjfwg7z9oiZH_"><p>Write a function named <code>substring_between_letters</code> that takes a string named <code>word</code>, a single character named <code>start</code>, and another character named <code>end</code>. This function should return the substring between the first occurrence of <code>start</code> and <code>end</code> in <code>word</code>. If <code>start</code> or <code>end</code> are not in <code>word</code>, the function should return <code>word</code>.</p>
<p>For example, <code>substring_between_letters("apple", "p", "e")</code> should return <code>"pl"</code>.</p>
</div>

```python

```
