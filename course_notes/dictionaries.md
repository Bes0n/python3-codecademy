## Introduction

<div class="theme__22QeW-d-YRjfwg7z9oiZH_"><p>This lesson will help you review Python functions by providing some challenge exercises involving dictionaries.</p>
<p>As a refresher, function syntax looks like this:</p>
<pre><code class="lang-py"><span language="py" class="CodeBlock__3-kebd7REMI5aXkez6K-B wrap__yxnEyEmMpigk6-3_Wvbzo defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined" data-reactroot=""><div class="CodeMirror"><span class="cm-keyword">def</span> <span class="cm-def">some_function</span>(<span class="cm-variable">some_input1</span>,<!-- --> <span class="cm-variable">some_input2</span>)<!-- -->:<!-- -->
<!-- -->  <span class="cm-variable">…</span> <span class="cm-variable">do</span> <span class="cm-variable">something</span> <span class="cm-keyword">with</span> <span class="cm-variable">the</span> <span class="cm-variable">inputs</span> <span class="cm-variable">…</span>
<!-- -->  <span class="cm-keyword">return</span> <span class="cm-variable">output</span></div></span>
</code></pre>
<p>For example, a function that counts the number of values in a dictionary that are above a given number would look like this:</p>
<pre><code class="lang-py"><span language="py" class="CodeBlock__3-kebd7REMI5aXkez6K-B wrap__yxnEyEmMpigk6-3_Wvbzo defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined" data-reactroot=""><div class="CodeMirror"><span class="cm-keyword">def</span> <span class="cm-def">greater_than_ten</span>(<span class="cm-variable">my_dictionary</span>,<!-- --> <span class="cm-variable">number</span>)<!-- -->:<!-- -->
<!-- -->  <span class="cm-variable">count</span> <span class="cm-operator">=</span> <span class="cm-number">0</span>
<!-- -->  <span class="cm-keyword">for</span> <span class="cm-variable">value</span> <span class="cm-keyword">in</span> <span class="cm-variable">my_dictionary</span>.<span class="cm-property">values</span>(<!-- -->)<!-- -->:<!-- -->
<!-- -->    <span class="cm-keyword">if</span> <span class="cm-variable">value</span> <span class="cm-operator">&gt;</span> <span class="cm-variable">number</span>:<!-- -->
<!-- -->      <span class="cm-variable">count</span> <span class="cm-operator">+=</span> <span class="cm-number">1</span>
<!-- -->  <span class="cm-keyword">return</span> <span class="cm-variable">count</span></div></span>
</code></pre>
<p>And this would produce output like:</p>
<pre><code><span class="CodeBlock__3-kebd7REMI5aXkez6K-B wrap__yxnEyEmMpigk6-3_Wvbzo defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined" data-reactroot=""><div class="CodeMirror">&gt;&gt;&gt; greater_than_ten({"a":1, "b":2, "c":3}, 0)<!-- -->
<!-- -->3<!-- -->
<!-- -->&gt;&gt;&gt; greater_than_ten({"a":1, "b":2, "c":3}, 5)<!-- -->
<!-- -->0</div></span>
</code></pre></div>

### Sum Values
sum_values()

###### TASK
<p>Write a function named <code>sum_values</code> that takes a dictionary named <code>my_dictionary</code> as a parameter. The function should return the sum of the values of the dictionary</p>

```python 
# Write your sum_values function here:
def sum_values(my_dictionary):
  total = 0
  for values in my_dictionary.values():
    total += values
  return total
# Uncomment these function calls to test your sum_values function:
print(sum_values({"milk":5, "eggs":2, "flour": 3}))
# should print 10
print(sum_values({10:1, 100:2, 1000:3}))
# should print 6
```

### Even Keys
sum_even_keys()

###### TASK
<p>Create a function called <code>sum_even_keys</code> that takes a dictionary named <code>my_dictionary</code>, with all integer keys and values, as a parameter. This function should return the sum of the values of all even keys.</p>

```python 
# Write your sum_even_keys function here:
def sum_even_keys(my_dictionary):
  total = 0
  for key in my_dictionary.keys():
    if key % 2 == 0:
      total += my_dictionary[key]
  return total
# Uncomment these function calls to test your  function:
print(sum_even_keys({1:5, 2:2, 3:3}))
# should print 2
print(sum_even_keys({10:1, 100:2, 1000:3}))
# should print 6
```

### Add Ten
add_ten()

###### TASK
<p>Create a function named <code>add_ten</code> that takes a dictionary with integer values named <code>my_dictionary</code> as a parameter. The function should add <code>10</code> to every value in <code>my_dictionary</code> and return <code>my_dictionary</code></p>

```python 
# Write your add_ten function here:
def add_ten(my_dictionary):
  for number in my_dictionary.keys():
    my_dictionary[number] += 10
  return my_dictionary

# Uncomment these function calls to test your  function:
print(add_ten({1:5, 2:2, 3:3}))
# should print {1:15, 2:12, 3:13}
print(add_ten({10:1, 100:2, 1000:3}))
# should print {10:11, 100:12, 1000:13}
```

### Values That Are Keys 
values_that_are_keys()

###### TASK
<p>Create a function named <code>values_that_are_keys</code> that takes a dictionary named <code>my_dictionary</code> as a parameter. This function should return a list of all values in the dictionary that are also keys.</p>

```python 
# Write your values_that_are_keys function here:
def values_that_are_keys(my_dictionary):
  values_keys = []
  for values in my_dictionary.values():
    if values in my_dictionary.keys():
      values_keys.append(values)
  return values_keys
# Uncomment these function calls to test your  function:
print(values_that_are_keys({1:100, 2:1, 3:4, 4:10}))
# should print [1, 4]
print(values_that_are_keys({"a":"apple", "b":"a", "c":100}))
# should print ["a"]
```

### Largest Value
max_key()

###### TASK
<p>Write a function named <code>max_key</code> that takes a dictionary named <code>my_dictionary</code> as a parameter. The function should return the key associated with the largest value in the dictionary.</p>

```python
# Write your max_key function here:
def max_key(my_dictionary):
  max_key = 0
  max_number = 0 
  for keys, values in my_dictionary.items():
    if values > max_number:
      max_number = values
      max_key = keys
  return max_key
      
# Uncomment these function calls to test your  function:
print(max_key({1:100, 2:1, 3:4, 4:10}))
# should print 1
print(max_key({"a":100, "b":10, "c":1000}))
# should print "c"
```

### Word Length Dict
word_length_dictionary()

```python
# Write your word_length_dictionary function here:
def word_length_dictionary(words):
  word_dict = {}
  for word in words:
    word_dict[word] = len(word)
  return word_dict
# Uncomment these function calls to test your  function:
print(word_length_dictionary(["apple", "dog", "cat"]))
# should print {"apple":5, "dog": 3, "cat":3}
print(word_length_dictionary(["a", ""]))
# should print {"a": 1, "": 0}
```

### Frequency Count
frequency_dictionary()

###### TASK
<p>Write a function named <code>frequency_dictionary</code> that takes a list of elements named <code>words</code> as a parameter. The function should return a dictionary containing the frequency of each element in <code>words</code>.</p>

```python
# Write your frequency_dictionary function here:
def frequency_dictionary(words):
  freq_dict = {}
  for word in words:
    if word not in freq_dict.keys():
      freq_dict[word] = 1
    else:
      freq_dict[word] += 1
  return freq_dict
      
# Uncomment these function calls to test your  function:
print(frequency_dictionary(["apple", "apple", "cat", 1]))
# should print {"apple":2, "cat":1, 1:1}
print(frequency_dictionary([0,0,0,0,0]))
# should print {0:5}
```

### Unique Values
unique_values()

###### TASK
<div class="theme__22QeW-d-YRjfwg7z9oiZH_"><p>Create a function named <code>unique_values</code> that takes a dictionary named <code>my_dictionary</code> as a parameter. The function should return the number of unique values in the dictionary.</p>
</div>

```python 
# Write your unique_values function here:
def unique_values(my_dictionary):
  unique_numbers = []
  for keys,values in my_dictionary.items():
    if values not in unique_numbers:
      unique_numbers.append(values)
  return len(unique_numbers)
# Uncomment these function calls to test your  function:
print(unique_values({0:3, 1:1, 4:1, 5:3}))
# should print 2
print(unique_values({0:3, 1:3, 4:3, 5:3}))
# should print 1
```


### Count First Letter
count_first_letter()

###### TASK
<div class="theme__22QeW-d-YRjfwg7z9oiZH_"><p>Create a function named <code>count_first_letter</code> that takes a dictionary named <code>names</code> as a parameter. <code>names</code> should be a dictionary where the key is a last name and the value is a list of first names. For example, the dictionary might look like this:</p>
<pre><code class="lang-py"><span language="py" class="CodeBlock__3-kebd7REMI5aXkez6K-B wrap__yxnEyEmMpigk6-3_Wvbzo defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined" data-reactroot=""><div class="CodeMirror"><span class="cm-variable">names</span> <span class="cm-operator">=</span> <!-- -->{<span class="cm-string">"Stark"</span>:<!-- --> <!-- -->[<span class="cm-string">"Ned"</span>,<!-- --> <span class="cm-string">"Robb"</span>,<!-- --> <span class="cm-string">"Sansa"</span>]<!-- -->,<!-- --> <span class="cm-string">"Snow"</span> <!-- -->:<!-- --> <!-- -->[<span class="cm-string">"Jon"</span>]<!-- -->,<!-- --> <span class="cm-string">"Lannister"</span>:<!-- --> <!-- -->[<span class="cm-string">"Jaime"</span>,<!-- --> <span class="cm-string">"Cersei"</span>,<!-- --> <span class="cm-string">"Tywin"</span>]<!-- -->}</div></span>
</code></pre>
<p>The function should return a new dictionary where each key is the first letter of a last name, and the value is the number of people whose last name begins with that letter.</p>
<p>So in example above, the function would return:</p>
<pre><code class="lang-py"><span language="py" class="CodeBlock__3-kebd7REMI5aXkez6K-B wrap__yxnEyEmMpigk6-3_Wvbzo defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined" data-reactroot=""><div class="CodeMirror">{<span class="cm-string">"S"</span> <!-- -->:<!-- --> <span class="cm-number">4</span>,<!-- --> <span class="cm-string">"L"</span>:<!-- --> <span class="cm-number">3</span>}</div></span>
</code></pre>
</div>


```python
# Write your count_first_letter function here:
def count_first_letter(names):
  first_letter = {}
  for keys,values in names.items():
    if keys[0] not in first_letter.keys():
      first_letter[keys[0]] = len(values)
    else:
      first_letter[keys[0]] += len(values)
  return first_letter
# Uncomment these function calls to test your  function:
print(count_first_letter({"Stark": ["Ned", "Robb", "Sansa"], "Snow" : ["Jon"], "Lannister": ["Jaime", "Cersei", "Tywin"]}))
# should print {"S": 4, "L": 3}
print(count_first_letter({"Stark": ["Ned", "Robb", "Sansa"], "Snow" : ["Jon"], "Sannister": ["Jaime", "Cersei", "Tywin"]}))
# should print {"S": 7}

```

