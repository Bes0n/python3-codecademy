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
# Write your substring_between_letters function here:

# Uncomment these function calls to test your function:
def substring_between_letters(word, start, end):
  start_index = word.find(start)
  end_index = word.find(end)
  if start_index == -1 or end_index == -1:
    return word
  else:
    return word[start_index+1:end_index]
  
print(substring_between_letters("apple", "p", "e"))
# should print "pl"
print(substring_between_letters("apple", "p", "c"))
# should print "apple"
```

### X Length
x_length_words()

###### TASK
<p>Create a function called <code>x_length_words</code> that takes a string named <code>sentence</code> and an integer named <code>x</code> as parameters. This function should return <code>True</code> if every word in <code>sentence</code> has a length greater than or equal to <code>x</code>.</p>

```python
# Write your x_length_words function here:
def x_length_words(sentence,x):
  sentence = sentence.split(" ")
  for item in sentence:
    if len(item) == x:
      return True
    else:
      return False
# Uncomment these function calls to test your tip function:
print(x_length_words("i like apples", 2))
# should print False
print(x_length_words("he likes apples", 2))
# should print True
```

### Check Name
check_for_name()

###### TASK
<div class="theme__22QeW-d-YRjfwg7z9oiZH_"><p>Write a function called <code>check_for_name</code> that takes two strings as parameters named <code>sentence</code> and <code>name</code>. The function should return <code>True</code> if <code>name</code> appears in <code>sentence</code> in all lowercase letters, all uppercase letters, or with any mix of uppercase and lowercase letters. The function should return <code>False</code> otherwise.</p>
<p>For example, the following three calls should all return <code>True</code>:</p>
<pre><code class="lang-py"><span language="py" class="CodeBlock__3-kebd7REMI5aXkez6K-B wrap__yxnEyEmMpigk6-3_Wvbzo defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined" data-reactroot=""><div class="CodeMirror"><span class="cm-variable">check_for_name</span>(<span class="cm-string">"My name is Jamie"</span>,<!-- --> <span class="cm-string">"Jamie"</span>)<!-- -->
<span class="cm-variable">check_for_name</span>(<span class="cm-string">"My name is jamie"</span>,<!-- --> <span class="cm-string">"Jamie"</span>)<!-- -->
<span class="cm-variable">check_for_name</span>(<span class="cm-string">"My name is JAMIE"</span>,<!-- --> <span class="cm-string">"Jamie"</span>)</div></span>
</code></pre>
</div>

```python
# Write your check_for_name function here:
def check_for_name(sentence,name):
  sentence = sentence.lower().split(" ")
  name = name.lower()
  if name in sentence:
    return True
  else:
    return False

# Uncomment these function calls to test your  function:
print(check_for_name("My name is Jamie", "Jamie"))
# should print True
print(check_for_name("My name is jamie", "Jamie"))
# should print True
print(check_for_name("My name is Samantha", "Jamie"))
# should print False

```

### Every Other Letter
every_other_letter()

###### TASK
<p>Create a function named <code>every_other_letter</code> that takes a string named <code>word</code> as a parameter. The function should return a string containing every other letter in <code>word</code>.</p>

```python
# Write your every_other_letter function here:
def every_other_letter(word):
  return word[::2]
# Uncomment these function calls to test your function:
print(every_other_letter("Codecademy"))
# should print Cdcdm
print(every_other_letter("Hello world!"))
# should print Hlowrd
print(every_other_letter(""))
# should print 
```

### Reverse
reverse_string()

###### TASK
<p>Write a function named <code>reverse_string</code> that has a string named <code>word</code> as a parameter. The function should return <code>word</code> in reverse.</p>

```python 
# Write your reverse_string function here:
def reverse_string(word):
  reverse_word = ""
  for index in range(len(word)):
    reverse_word += word[-(index + 1)]
  return reverse_word
# Uncomment these function calls to test your  function:
print(reverse_string("Codecademy"))
# should print ymedacedoC
print(reverse_string("Hello world!"))
# should print !dlrow olleH
print(reverse_string(""))
# should print
```

### Make Spoonerism
make_spoonerism()

###### TASK
<div class="theme__22QeW-d-YRjfwg7z9oiZH_"><p>A <a href="https://en.wikipedia.org/wiki/Spoonerism" target="_blank">Spoonerism</a> is an error in speech when the first syllables of two words are switched. For example, a Spoonerism is made when someone says "Belly Jeans" instead of "Jelly Beans". </p>
<p>Write a function called <code>make_spoonerism</code> that takes two strings as parameters named <code>word1</code> and <code>word2</code>. Finding the first syllable of a word is a difficult task, so for our function, we're going to switch the first letters of each word. Return the two new words as a single string separated by a space.</p>
</div>

```python 
# Write your make_spoonerism function here:

# Uncomment these function calls to test your function:
def make_spoonerism(word1, word2):
  index_word1 = word1[0]
  index_word2 = word2[0]
  return "{} {}".format(index_word2 + word1[1:len(word1)], index_word1 + word2[1:len(word2)])

print(make_spoonerism("Codecademy", "Learn"))
# should print Lodecademy Cearn
print(make_spoonerism("Hello", "world!"))
# should print wello Horld!
print(make_spoonerism("a", "b"))
# should print b a
```

### Add Exclamation
add_exclamation()

###### TASK
<p>Create a function named <code>add_exclamation</code> that has one parameter named <code>word</code>. This function should add exclamation points to the end of <code>word</code> until <code>word</code> is <code>20</code> characters long. If <code>word</code> is already at least <code>20</code> characters long, just return <code>word</code>.</p>

```python
# Write your add_exclamation function here:
def add_exclamation(word):
  if len(word) <= 20:
    return word + "!!!!!!!!!!"
  else:
    return word
# Uncomment these function calls to test your function:
#print(add_exclamation("Codecademy"))
# should print Codecademy!!!!!!!!!!
#print(add_exclamation("Codecademy is the best place to learn"))
# should print Codecademy is the best place to learn
```

