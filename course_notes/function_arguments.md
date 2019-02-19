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
* <p>Grab a new review using <code>get_next_review()</code>. Save the results into a variable called <code>review</code>.</p>

* <p>Check if there is a <code>review</code> by comparing it against <code>None</code>. If <code>review</code> contains a value that isn't <code>None</code>, submit it by calling the function <code>submit_review()</code> with <code>review</code> as an argument.</p>

```python
from review_lib import get_next_review, submit_review

# define review here!
review = get_next_review()
if review is not None:
  submit_review(review)
```


### Default Return
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>What does a function return when it doesn't return anything? This sounds like a riddle, but there is a correct answer. A Python function that does not have any explicit <code>return</code> statement will return <code>None</code> after completing. This means that all functions in Python return something, whether it's explicit or not. For example:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">def</span> <span class="cm-def">no_return</span>():
  <span class="cm-builtin">print</span>(<span class="cm-string">"You've hit the point of no return"</span>)
  <span class="cm-comment"># notice no return statement</span>

<span class="cm-variable">here_it_is</span> <span class="cm-operator">=</span> <span class="cm-variable">no_return</span>()

<span class="cm-builtin">print</span>(<span class="cm-variable">here_it_is</span>)
<span class="cm-comment"># Prints out "None"</span></div></span></pre>
<p>Above we defined a function called <code>no_return()</code> and saved the result to a variable <code>here_it_is</code>. When we <code>print()</code> the value of <code>here_it_is</code> we get <code>None</code>, referring to Python's <code>None</code>. It's possible to make this syntax even more explicit — a <code>return</code> statement without any value returns <code>None</code> also.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">def</span> <span class="cm-def">fifty_percent_off</span>(<span class="cm-variable">item</span>):
  <span class="cm-comment"># Check if item.cost exists</span>
  <span class="cm-keyword">if</span> <span class="cm-builtin">hasattr</span>(<span class="cm-variable">item</span>, <span class="cm-string">'cost'</span>):
    <span class="cm-keyword">return</span> <span class="cm-variable">item</span>.<span class="cm-property">cost</span> <span class="cm-operator">/</span> <span class="cm-number">2</span>

  <span class="cm-comment"># If not, return None </span>
  <span class="cm-keyword">return</span>

<span class="cm-variable">sale_price</span> <span class="cm-operator">=</span> <span class="cm-variable">return_half_of_cost</span>(<span class="cm-variable">product</span>)

<span class="cm-keyword">if</span> <span class="cm-variable">sale_price</span> <span class="cm-keyword">is</span> <span class="cm-keyword">None</span>:
  <span class="cm-builtin">print</span>(<span class="cm-string">"This product is not for sale!"</span>)</div></span></pre>
<p>Here we have implemented a function that returns the cost of a product with "50% Off" (or "half price"). We check if the <code>item</code> passed to our function has a <code>cost</code> attribute. If it exists, we return half the cost. If not, we simply <code>return</code>, which returns <code>None</code>.</p>
<p>When we plug a product into this function, we can expect two possibilities: the first is that the <code>item</code> has a cost and this function returns half of that. The other is that <code>item</code> does not have a listed cost and so the function returns <code>None</code>. We can put error handling in the rest of our code, if we get <code>None</code> back from this function that means whatever we're looking at isn't for sale!</p>
</div>


###### TASK
* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Lots of everyday Python functions return <code>None</code>. What's the return value of a call to <code>print()</code>? Since <code>print()</code> is a function it must return something.</p>
<p>Create a variable called <code>prints_return</code> and set it equal to a print statement. Make sure to give the print statement parentheses and give it an argument (like "hi!").</p>
</div>

* <p>Now print out <code>prints_return</code>.</p>

* <p>Inside <strong>script.py</strong> is a list called <code>sort_this_list</code>. Create a new variable called <code>list_sort_return</code> and set it equal to <code>sort_this_list.sort()</code>.</p>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>What do you expect <code>list_sort_return</code> to contain? </p>
<p>Print out <code>list_sort_return</code>.</p>
</div>

```python
# store the result of this print() statement in the variable prints_return
prints_return = print("What does this print function return?")

# print out the value of prints_return
print(prints_return)

# call sort_this_list.sort() and save that in list_sort_return
sort_this_list = [14, 631, 4, 51358, 50000000]
list_sort_return = sort_this_list.sort()

# print out the value of list_sort_return
print(list_sort_return)


```

### Default Arguments
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Function arguments are required in Python. So a standard function definition that defines two parameters requires two arguments passed into the function.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-comment"># Function definition with two required parameters</span>
<span class="cm-keyword">def</span> <span class="cm-def">create_user</span>(<span class="cm-variable">username</span>, <span class="cm-variable">is_admin</span>):
  <span class="cm-variable">create_email</span>(<span class="cm-variable">username</span>)
  <span class="cm-variable">set_permissions</span>(<span class="cm-variable">is_admin</span>)

<span class="cm-comment"># Function call with all two required arguments</span>
<span class="cm-variable">user1</span> <span class="cm-operator">=</span> <span class="cm-variable">create_user</span>(<span class="cm-string">'johnny_thunder'</span>, <span class="cm-keyword">True</span>)

<span class="cm-comment"># Raises a "TypeError: Missing 1 required positional argument"</span>
<span class="cm-variable">user2</span> <span class="cm-operator">=</span> <span class="cm-variable">create_user</span>(<span class="cm-string">'djohansen'</span>)</div></span></pre>
<p>Above we defined our function, <code>create_user</code>, with two parameters. We first called it with two arguments, but then tried calling it with only one argument and got an error. What if we had sensible defaults for this argument? </p>
<p>Not all function arguments in Python need to be required. If we give a default argument to a Python function that argument won't be required when we call the function.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-comment"># Function defined with one required and one optional parameter</span>
<span class="cm-keyword">def</span> <span class="cm-def">create_user</span>(<span class="cm-variable">username</span>, <span class="cm-variable">is_admin</span><span class="cm-operator">=</span><span class="cm-keyword">False</span>):
  <span class="cm-variable">create_email</span>(<span class="cm-variable">username</span>)
  <span class="cm-variable">set_permissions</span>(<span class="cm-variable">is_admin</span>)

<span class="cm-comment"># Calling with two arguments uses the default value for is_admin</span>
<span class="cm-variable">user2</span> <span class="cm-operator">=</span> <span class="cm-variable">create_user</span>(<span class="cm-string">'djohansen'</span>)</div></span></pre>
<p>Above we defined <code>create_user</code> with a default argument for <code>is_admin</code>, so we can call that function with only the one argument <code>'djohansen'</code>. It assumes the default value for <code>is_admin</code> &amp;mdash <code>False</code>. We can make both of our parameters have a default value (therefore making them all optional).</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-comment"># We can make all three parameters optional</span>
<span class="cm-keyword">def</span> <span class="cm-def">create_user</span>(<span class="cm-variable">username</span><span class="cm-operator">=</span><span class="cm-keyword">None</span>, <span class="cm-variable">is_admin</span><span class="cm-operator">=</span><span class="cm-keyword">False</span>):
  <span class="cm-keyword">if</span> <span class="cm-variable">username</span> <span class="cm-keyword">is</span> <span class="cm-keyword">None</span>:
    <span class="cm-variable">username</span> <span class="cm-operator">=</span> <span class="cm-string">"Guest"</span>
  <span class="cm-keyword">else</span>:
    <span class="cm-variable">create_email</span>(<span class="cm-variable">username</span>)
  <span class="cm-variable">set_permissions</span>(<span class="cm-variable">is_admin</span>)

<span class="cm-comment"># So we can call with just one value</span>
<span class="cm-variable">user3</span> <span class="cm-operator">=</span> <span class="cm-variable">create_user</span>(<span class="cm-string">'ssylvain'</span>)
<span class="cm-comment"># Or no value at all, which would create a Guest user</span>
<span class="cm-variable">user4</span> <span class="cm-operator">=</span> <span class="cm-variable">create_user</span>()</div></span></pre>
<p>Above we define the function with all optional parameters, if we call it with one argument that gets interpreted as <code>username</code>. We can call it without any arguments at all, which would only use the default values. </p>
</div>

###### TASK
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>In <strong>script.py</strong> there is a function called <code>make_folders()</code>. We want to add a default argument to the <code>nest</code> parameter in <code>make_folders()</code>. </p>
<p>Set is so that if we call <code>make_folders()</code> without an argument for <code>nest</code> the function assumes it gets a value of <code>False</code>.</p>
</div>

```python
import os

def make_folders(folders_list, nest=False):
  if nest:
    """
    Nest all the folders, like
    ./Music/fun/parliament
    """
    path_to_new_folder = ""
    for folder in folders_list:
      path_to_new_folder += "/{}".format(folder)
      try:
        os.makedirs(path_to_new_folder)
      except FileExistsError:
        continue
  else:
    """
    Makes all different folders, like
    ./Music/ ./fun/ and ./parliament/
    """
    for folder in folders_list:
      try:
        os.makedirs(folder)

      except FileExistsError:
        continue

make_folders(['./Music', './fun', './parliament'])

```

### Using Keyword and Positional Arguments
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Not all of your arguments need to have default values. But Python will only accept functions defined with their parameters in a specific order. The required parameters need to occur before any parameters with a default argument.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-comment"># Raises a TypeError</span>
<span class="cm-keyword">def</span> <span class="cm-def">create_user</span>(<span class="cm-variable">is_admin</span><span class="cm-operator">=</span><span class="cm-keyword">False</span>, <span class="cm-variable">username</span>, <span class="cm-variable">password</span>):
  <span class="cm-variable">create_email</span>(<span class="cm-variable">username</span>, <span class="cm-variable">password</span>)
  <span class="cm-variable">set_permissions</span>(<span class="cm-variable">is_admin</span>)</div></span></pre>
<p>In the above code, we attempt to define a default argument for <code>is_admin</code> without defining default arguments for the later parameters: <code>username</code> and <code>password</code>. </p>
<p>If we want to give <code>is_admin</code> a default argument, we need to list it last in our function definition:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-comment"># Works perfectly</span>
<span class="cm-keyword">def</span> <span class="cm-def">create_user</span>(<span class="cm-variable">username</span>, <span class="cm-variable">password</span>, <span class="cm-variable">is_admin</span><span class="cm-operator">=</span><span class="cm-keyword">False</span>):
  <span class="cm-variable">create_email</span>(<span class="cm-variable">username</span>, <span class="cm-variable">password</span>)
  <span class="cm-variable">set_permissions</span>(<span class="cm-variable">is_admin</span>)</div></span></pre>
</div>


###### TASK
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>In <strong>script.py</strong> the function <code>get_id</code> tries to define a parameter with a default argument before a required parameter.</p>
<p>Update the <em>function signature</em> of <code>get_id</code> so that <code>website</code> comes second and <code>html_id</code> comes first.</p>
</div>

```python
import reqs as requests
from bs4 import BeautifulSoup

def get_id(html_id, website="http://coolsite.com"):
  request = requests.get(website)
  parsed_html = BeautifulSoup(website.content, features="html.parser")
  return parsed_html.find(id_=html_id)

```

### Keyword Arguments
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>When we call a function in Python, we need to list the arguments to that function to match the order of the parameters in the function definition. We don't necessarily need to do this if we pass keyword arguments.</p>
<p>We use <em>keyword arguments</em> by passing arguments to a function with a special syntax that uses the names of the parameters. This is useful if the function has many optional default arguments or if the order of a function's parameters is hard to tell. Here's an example of a function with a lot of optional arguments.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-comment"># Define a function with a bunch of default arguments</span>
<span class="cm-keyword">def</span> <span class="cm-def">log_message</span>(<span class="cm-variable">logging_style</span><span class="cm-operator">=</span><span class="cm-string">"shout"</span>, <span class="cm-variable">message</span><span class="cm-operator">=</span><span class="cm-string">""</span>, <span class="cm-variable">font</span><span class="cm-operator">=</span><span class="cm-string">"Times"</span>, <span class="cm-variable">date</span><span class="cm-operator">=</span><span class="cm-keyword">None</span>):
  <span class="cm-keyword">if</span> <span class="cm-variable">logging_style</span> <span class="cm-operator">==</span> <span class="cm-string">'shout'</span>:
    <span class="cm-comment"># capitalize the message</span>
    <span class="cm-variable">message</span> <span class="cm-operator">=</span> <span class="cm-variable">message</span>.<span class="cm-property">upper</span>()
  <span class="cm-builtin">print</span>(<span class="cm-variable">message</span>, <span class="cm-variable">date</span>)

<span class="cm-comment"># Now call the function with keyword arguments</span>
<span class="cm-variable">log_message</span>(<span class="cm-variable">message</span><span class="cm-operator">=</span><span class="cm-string">"Hello from the past"</span>, <span class="cm-variable">date</span><span class="cm-operator">=</span><span class="cm-string">"November 20, 1693"</span>)</div></span></pre>
<p>Above we defined <code>log_message()</code>, which can take from 0 to 4 arguments. Since it's not clear which order the four arguments might be defined in, we can use the parameter names to call the function. Notice that in our function call we use this syntax: <code>message="Hello from the past"</code>. The key word <code>message</code> here needs to be the name of the parameter we are trying to pass the argument to.</p>
</div>

###### TASK
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>In <strong>script.py</strong> we've defined a <code>draw_shape()</code> function that will draw a shape to the terminal! Call <code>draw_shape()</code> with <code>"m"</code> as the <code>character</code> and <code>line_breaks</code> set to <code>False</code>.</p>
</div>

```python
import shapes

def draw_shape(shape_name="box", character="x", line_breaks=True):
  shape = shapes.draw_shape(shape_name, character)
  if not line_breaks:
    print(shape[1:-1])
  else:
    print(shape)

# call draw_shape() with keyword arguments here:
draw_shape(character="m", line_breaks=False)

```

### Don't Use Mutable Default Arguments
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>When writing a function with default arguments, it can be tempting to include an empty list as a default argument to that function. Let's say you have a function called <code>populate_list</code> that has two required arguments, but it's easy to see that we might want to give it some default arguments in case we don't have either <code>list_to_populate</code> or <code>length</code> every time. So we'd give it these defaults:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">def</span> <span class="cm-def">populate_list</span>(<span class="cm-variable">list_to_populate</span><span class="cm-operator">=</span>[], <span class="cm-variable">length</span><span class="cm-operator">=</span><span class="cm-number">1</span>):
  <span class="cm-keyword">for</span> <span class="cm-variable">num</span> <span class="cm-keyword">in</span> <span class="cm-builtin">range</span>(<span class="cm-variable">length</span>):
    <span class="cm-variable">list_to_populate</span>.<span class="cm-property">append</span>(<span class="cm-variable">num</span>)
  <span class="cm-keyword">return</span> <span class="cm-variable">list_to_populate</span></div></span></pre>
<p>It's reasonable to believe that <code>list_to_populate</code> will be given an empty list every time it's called. This isn't the case! <code>list_to_populate</code> will be given a new list once, in its definition, and all subsequent function calls will modify the same list. This will happen:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-variable">returned_list</span> <span class="cm-operator">=</span> <span class="cm-variable">populate_list</span>(<span class="cm-variable">length</span><span class="cm-operator">=</span><span class="cm-number">4</span>)
<span class="cm-builtin">print</span>(<span class="cm-variable">returned_list</span>)
<span class="cm-comment"># Prints [0, 1, 2, 3] -- this is expected</span>

<span class="cm-variable">returned_list</span> <span class="cm-operator">=</span> <span class="cm-variable">populate_list</span>(<span class="cm-variable">length</span><span class="cm-operator">=</span><span class="cm-number">6</span>)
<span class="cm-builtin">print</span>(<span class="cm-variable">returned_list</span>)
<span class="cm-comment"># Prints [0, 1, 2, 3, 0, 1, 2, 3, 4, 5] -- this is a surprise!</span></div></span></pre>
<p>When we call <code>populate_list</code> a second time we'd expect the list <code>[0, 1, 2, 3, 4, 5]</code>. But the same list is used both times the function is called, causing some side-effects from the first function call to creep into the second. This is because a list is a mutable object.</p>
<p>A <em>mutable object</em> refers to various data structures in Python that are intended to be mutated, or changed. A list has append and remove operations that change the nature of a list. Sets and dictionaries are two other mutable objects in Python.</p>
<p>It might be helpful to note some of the objects in Python that are not mutable (and therefore OK to use as default arguments). <code>int</code>, <code>float</code>, and other numbers can't be mutated (arithmetic operations will return a new number). <code>tuple</code>s are a kind of immutable list. Strings are also immutable — operations that update a string will all return a completely new string.</p>
</div>

###### TASK
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>In <strong>script.py</strong> we've written a helper function that adds a new menu item to an order in a point-of-sale system. As you can see, we can start a new order by calling <code>update_order</code> without an argument for <code>current_order</code>. Unfortunately, there's a bug in our code causing some previous order contents to show up on other people's bills!</p>
<p>First, try to guess what the output of this code will be. Then, run <strong>script.py</strong>.</p>
<p>We'll fix this function in the next exercise, if you want more of an explanation of what's happening here, check out the hint!</p>
</div>

```python
def update_order(new_item, current_order=[]):
  current_order.append(new_item)
  return current_order

# First order, burger and a soda
order1 = update_order({'item': 'burger', 'cost': '3.50'})
order1 = update_order({'item': 'soda', 'cost': '1.50'}, order1)

# Second order, just a soda
order2 = update_order({'item': 'soda', 'cost': '1.50'})

# What's in that second order again?
print(order2)

```

### Using None as a Sentinel
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>So if we can't use a list as a default argument for a function, what can we use? If we want an empty list, we can use <code>None</code> as a special value to indicate we did not receive anything. After we check whether an argument was provided we can instantiate a new list if it wasn't.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">def</span> <span class="cm-def">add_author</span>(<span class="cm-variable">authors_books</span>, <span class="cm-variable">current_books</span><span class="cm-operator">=</span><span class="cm-keyword">None</span>):
  <span class="cm-keyword">if</span> <span class="cm-variable">current_books</span> <span class="cm-keyword">is</span> <span class="cm-keyword">None</span>:
    <span class="cm-variable">current_books</span> <span class="cm-operator">=</span> []

  <span class="cm-variable">current_books</span>.<span class="cm-property">extend</span>(<span class="cm-variable">authors_books</span>)
  <span class="cm-keyword">return</span> <span class="cm-variable">current_books</span></div></span></pre>
<p>In the above function, we accept <code>current_books</code> a value expected to be a list. But we don't require it. If someone calls <code>add_author()</code> without giving an argument for <code>current_books</code>, we supply an empty list. This way multiple calls to <code>add_author</code> won't include data from previous calls to <code>add_author</code>.</p>
</div>

###### TASK
<p>Update the function so that calls to <code>update_order</code> don't have side-effects — no order should affect other orders.</p>

```python
def update_order(new_item, current_order=None):
  if current_order is None:  
    current_order = []
  current_order.append(new_item)
  return current_order

# First order, burger and a soda
order1 = update_order({'item': 'burger', 'cost': '3.50'})
order1 = update_order({'item': 'soda', 'cost': '1.50'}, order1)

# Second order, just a soda
order2 = update_order({'item': 'soda', 'cost': '1.50'})

# What's in that second order again?
print(order2)
```

### Unpacking Multiple Returns
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>A Python function can return multiple things. This is especially useful in cases where bundling data into a different structure (a dictionary or a list, for instance) would be excessive. In Python we can return multiple pieces of data by separating each variable with a comma:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">def</span> <span class="cm-def">multiple_returns</span>(<span class="cm-variable">cool_num1</span>, <span class="cm-variable">cool_num2</span>):
  <span class="cm-variable">sum_nums</span> <span class="cm-operator">=</span> <span class="cm-variable">cool_num1</span> <span class="cm-operator">+</span> <span class="cm-variable">cool_num2</span>
  <span class="cm-variable">div_nums</span> <span class="cm-operator">=</span> <span class="cm-variable">cool_num1</span> <span class="cm-operator">/</span> <span class="cm-variable">cool_num2</span>
  <span class="cm-keyword">return</span> <span class="cm-variable">sum_nums</span>, <span class="cm-variable">div_nums</span></div></span></pre>
<p>Above we created a function that returns two results, <code>sum_nums</code> and <code>div_nums</code>. What happens when we call the function?</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-variable">sum_and_div</span> <span class="cm-operator">=</span> <span class="cm-variable">multiple_returns</span>(<span class="cm-number">20</span>, <span class="cm-number">10</span>)

<span class="cm-builtin">print</span>(<span class="cm-variable">sum_and_div</span>)
<span class="cm-comment"># Prints "(30, 2)"</span>

<span class="cm-builtin">print</span>(<span class="cm-variable">sum_and_div</span>[<span class="cm-number">0</span>])
<span class="cm-comment"># Prints "30"</span></div></span></pre>
<p>So we get those two values back in what's called a <em>tuple</em>, an immutable list-like object indicated by parentheses. We can index into the tuple the same way as a list and so <code>sum_and_div[0]</code> will give us our <code>sum_nums</code> value and <code>sum_and_div[1]</code> will produce our <code>div_nums</code> value.</p>
<p>What if we wanted to save these two results in separate variables? Well we can by <em>unpacking</em> the function return. We can list our new variables, comma-separated, that correspond to the number of values returned:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-builtin">sum</span>, <span class="cm-variable">div</span> <span class="cm-operator">=</span> <span class="cm-variable">sum_and_div</span>(<span class="cm-number">18</span>, <span class="cm-number">9</span>)

<span class="cm-builtin">print</span>(<span class="cm-builtin">sum</span>)
<span class="cm-comment"># Prints "27"</span>

<span class="cm-builtin">print</span>(<span class="cm-variable">div</span>)
<span class="cm-comment"># Prints "2"</span></div></span></pre>
<p>Above we were able to unpack the two values returned into separate variables.</p>
</div>

###### TASK
<p>In <strong>script.py</strong> you'll find the definition of the function <code>scream_and_whisper()</code>. Call the function with a string of your choice and store the results in <code>the_scream</code> and <code>the_whisper</code>.</p>

```python
def scream_and_whisper(text):
    scream = text.upper()
    whisper = text.lower()
    return scream, whisper

the_scream, the_whisper = scream_and_whisper("Shout 2000")
```

### Positional Argument Unpacking 
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>We don't always know how many arguments a function is going to receive, and sometimes we want to handle any possibility that comes at us. Python gives us two methods of unpacking arguments provided to functions. The first method is called <em>positional argument unpacking</em>, because it unpacks arguments given by position. Here's what that looks like:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">def</span> <span class="cm-def">shout_strings</span>(<span class="cm-operator">*</span><span class="cm-variable">args</span>):
  <span class="cm-keyword">for</span> <span class="cm-variable">argument</span> <span class="cm-keyword">in</span> <span class="cm-variable">args</span>:
    <span class="cm-builtin">print</span>(<span class="cm-variable">argument</span>.<span class="cm-property">upper</span>())

<span class="cm-variable">shout_strings</span>(<span class="cm-string">"hi"</span>, <span class="cm-string">"what do we have here"</span>, <span class="cm-string">"cool, thanks!"</span>)
<span class="cm-comment"># Prints out:</span>
<span class="cm-comment"># "HI"</span>
<span class="cm-comment"># "WHAT DO WE HAVE HERE"</span>
<span class="cm-comment"># "COOL, THANKS!"</span></div></span></pre>
<p>In <code>shout_strings()</code> we use a single asterisk (<code>*</code>) to indicate we'll accept any number of positional arguments passed to the function. Our parameter <code>args</code> is a tuple of all of the arguments passed. In this case <code>args</code> has three values inside, but it can have many more (or fewer). </p>
<p>Note that <code>args</code> is just a parameter name, and we aren't limited to that name (although it is rather standard practice). We can also have other positional parameters before our <code>*args</code> parameter. We can't, as we'll see, :</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">def</span> <span class="cm-def">truncate_sentences</span>(<span class="cm-variable">length</span>, <span class="cm-operator">*</span><span class="cm-variable">sentences</span>):
  <span class="cm-keyword">for</span> <span class="cm-variable">sentence</span> <span class="cm-keyword">in</span> <span class="cm-variable">sentences</span>:
    <span class="cm-builtin">print</span>(<span class="cm-variable">sentence</span>[:<span class="cm-variable">length</span>])

<span class="cm-variable">truncate_sentences</span>(<span class="cm-number">8</span>, <span class="cm-string">"What's going on here"</span>, <span class="cm-string">"Looks like we've been cut off"</span>)
<span class="cm-comment"># Prints out:</span>
<span class="cm-comment"># "What's g"</span>
<span class="cm-comment"># "Looks li"</span></div></span></pre>
<p>Above we defined a function <code>truncate_sentences</code> that takes a <code>length</code> parameter and also any number of <code>sentences</code>. The function prints out the first <code>length</code> many characters of each <code>sentence</code> in <code>sentences</code>.</p>
</div>

###### TASK
* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>The Python library <code>os.path</code> has a function called <code>join()</code>. <code>join()</code> takes an arbitrary number of paths as arguments.</p>
<p>Use the <code>join()</code> function to join all three of the path segments, and print out the results!</p>
</div>

* <p>Write your own function, called <code>myjoin()</code> which takes an arbitrary number of strings and appends them all together, similar to <code>os.path.join()</code>.</p>

```python
from os.path import join

path_segment_1 = "/Home/User"
path_segment_2 = "Codecademy/videos"
path_segment_3 = "cat_videos/surprised_cat.mp4"

# join all three of the paths here!
print(join(path_segment_1, path_segment_2, path_segment_3))
```


### Keyword Argument Unpacking
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Python doesn't stop at allowing us to accept unlimited positional parameters, it gives us the power to define functions with unlimited keyword parameters too. The syntax is very similar, but uses two asterisks (<code>**</code>) instead of one. Instead of <code>args</code>, we call this <code>kwargs</code> — as a shorthand for keyword arguments.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">def</span> <span class="cm-def">arbitrary_keyword_args</span>(<span class="cm-operator">*</span><span class="cm-operator">*</span><span class="cm-variable">kwargs</span>):
  <span class="cm-builtin">print</span>(<span class="cm-builtin">type</span>(<span class="cm-variable">kwargs</span>))
  <span class="cm-builtin">print</span>(<span class="cm-variable">kwargs</span>)
  <span class="cm-comment"># See if there's an "anything_goes" keyword arg</span>
  <span class="cm-comment"># and print it</span>
  <span class="cm-builtin">print</span>(<span class="cm-variable">kwargs</span>.<span class="cm-property">get</span>(<span class="cm-string">'anything_goes'</span>))

<span class="cm-variable">arbitrary_keyword_args</span>(<span class="cm-variable">this_arg</span><span class="cm-operator">=</span><span class="cm-string">"wowzers"</span>, <span class="cm-variable">anything_goes</span><span class="cm-operator">=</span><span class="cm-number">101</span>)
<span class="cm-comment"># Prints "&lt;class 'dict'&gt;</span>
<span class="cm-comment"># Prints "{'this_arg': 'wowzers', 'anything_goes': 101}"</span>
<span class="cm-comment"># Prints "101"</span></div></span></pre>
<p>As you can see, <code>**kwargs</code> gives us a dictionary with all the keyword arguments that were passed to <code>arbitrary_keyword_args</code>. We can access these arguments using standard dictionary methods. </p>
<p>Since we're not sure whether a keyword argument will exist, it's probably best to use the dictionary's <code>.get()</code> method to safely retrieve the keyword argument. Do you remember what <code>.get()</code> returns if the key is not in the dictionary? It's <code>None</code>!</p>
</div>

###### TASK
* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>The string <code>.format()</code> method can utilize keyword argument syntax if you give placeholder names in curly braces in a string. For example:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-string">"{place} is {adjective} this time of year."</span>.<span class="cm-property">format</span>(<span class="cm-variable">place</span><span class="cm-operator">=</span><span class="cm-string">"New York"</span>, <span class="cm-variable">adjective</span><span class="cm-operator">=</span><span class="cm-string">"quite cold, actually"</span>)</div></span></pre>
<p>Format the string in <strong>script.py</strong> within the <code>print()</code> statement. Give arguments for the placeholders given.</p>
</div>

* <p><code>create_products()</code> takes a dictionary object and iterates over it, we can change it so that it uses keyword arguments instead. Update this function signature so <code>products_dict</code> contains all the keyword arguments passed to <code>create_products()</code>.</p>

* <p>Update the call to <code>create_products()</code> to pass in each of those dictionary items as a keyword argument instead.</p>

```python
# Checkpoint 1
print("My name is {name} and I'm feeling {feeling}.".format(
	name="Tim",
  feeling="10/10",
))

# Checkpoint 2
from products import create_product

# Update create_products() to take arbitrary keyword arguments
def create_products(**products_dict):
  for name, price in products_dict.items():
    create_product(name, price)

# Checkpoint 3
# Update the call to `create_products()` to pass in this dictionary as a series of keyword
create_products(
  Baseball='3',
  Shirt='14',
  Guitar='70')
```

### Using Both Keyword and Positional Unpacking 
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>This keyword argument unpacking syntax can be used even if the function takes other parameters. However, the parameters must be listed in this order:</p>
<ul>
<li>All named positional parameters</li>
<li>An unpacked positional parameter (<code>*args</code>)</li>
<li>All named keyword parameters</li>
<li>An unpacked keyword parameter (<code>**kwargs</code>)</li>
</ul>
<p>Here's a function with all possible types of parameter:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">def</span> <span class="cm-def">main</span>(<span class="cm-variable">filename</span>, <span class="cm-operator">*</span><span class="cm-variable">args</span>, <span class="cm-variable">user_list</span><span class="cm-operator">=</span><span class="cm-keyword">None</span>, <span class="cm-operator">*</span><span class="cm-operator">*</span><span class="cm-variable">kwargs</span>):
  <span class="cm-keyword">if</span> <span class="cm-variable">user_list</span> <span class="cm-keyword">is</span> <span class="cm-keyword">None</span>:
    <span class="cm-variable">user_list</span> <span class="cm-operator">=</span> []

  <span class="cm-keyword">if</span> <span class="cm-string">'-a'</span> <span class="cm-keyword">in</span> <span class="cm-variable">args</span>:
    <span class="cm-variable">user_list</span> <span class="cm-operator">=</span> <span class="cm-variable">all_users</span>()

  <span class="cm-keyword">if</span> <span class="cm-variable">kwargs</span>.<span class="cm-property">get</span>(<span class="cm-string">'active'</span>):
    <span class="cm-variable">user_list</span> <span class="cm-operator">=</span> [<span class="cm-variable">user</span> <span class="cm-keyword">for</span> <span class="cm-variable">user_list</span> <span class="cm-keyword">if</span> <span class="cm-variable">user</span>.<span class="cm-property">active</span>]

  <span class="cm-keyword">with</span> <span class="cm-builtin">open</span>(<span class="cm-variable">filename</span>) <span class="cm-keyword">as</span> <span class="cm-variable">user_file</span>:
    <span class="cm-variable">user_file</span>.<span class="cm-property">write</span>(<span class="cm-variable">user_list</span>)</div></span></pre>
<p>Looking at the signature of <code>main()</code> we define four different kinds of parameters. 
The first, <code>filename</code> is a normal required positional parameter. 
The second, <code>*args</code>, is all positional arguments given to a function after that organized as a tuple in the parameter <code>args</code>. 
The third, <code>user_list</code>, is a keyword parameter with a default value. 
Lastly, <code>**kwargs</code> is all other keyword arguments assembled as a dictionary in the parameter <code>kwargs</code>.</p>
<p>A possible call to the function could look like this:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-variable">main</span>(<span class="cm-string">"files/users/userslist.txt"</span>, 
     <span class="cm-string">"-d"</span>, 
     <span class="cm-string">"-a"</span>, 
     <span class="cm-variable">save_all_records</span><span class="cm-operator">=</span><span class="cm-keyword">True</span>, 
     <span class="cm-variable">user_list</span><span class="cm-operator">=</span><span class="cm-variable">current_users</span>)</div></span></pre>
<p>In the body of <code>main()</code> these arguments would look like this:</p>
<ul>
<li><code>filename == "files/users/userslist.txt"</code></li>
<li><code>args == ('-d', '-a)</code></li>
<li><code>user_list == current_users</code></li>
<li><code>kwargs == {'save_all_records': True}</code></li>
</ul>
<p>We can use all four of these kinds of parameters to create functions that handle a lot of possible arguments being passed to them.</p>
</div>

###### TASK
* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>In <strong>script.py</strong> you'll find the function <code>remove()</code> has three parameters: the required positional <code>filename</code>, the arbitrary positional <code>args</code>, and the arbitrary keyword <code>kwargs</code>.</p>
<p>Before returning the text, we want to remove all arguments passed as positional arguments from the text. Using <code>text.replace()</code> change every <code>arg</code> in <code>args</code> into an empty string <code>""</code>.</p>
</div>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Now iterate over every <code>kwarg</code> and <code>replacement</code> in <code>kwargs.items()</code> (recall this is how to iterate over key-value pairs in a dictionary).</p>
<p>Replace every instance of <code>kwarg</code> with <code>replacement</code> in <code>text</code>.</p>
</div>

* <p>Now remove the bottom comment and see the text of <em>Robin Hood; Being A Complete History Of All The Notable And Merry Exploits Performed By Him And His Men, On Many Occasions.</em> by William Darton transformed!</p>

```python
def remove(filename, *args, **kwargs):
  with open(filename) as file_obj:
    text = file_obj.read()

  # Add code here to update text.
  for arg in args:
    text = text.replace(arg, '')
  
  for kwarg, replacement in kwargs.items():
    text = text.replace(kwarg, replacement)
  
  return text

print(remove("text.txt", "generous", "gallant", fond="amused by", Robin="Mr. Robin"))

```

### Passing Containers as Arguments
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Not only can we accept arbitrarily many parameters to a function in our definition, but Python also supports a syntax that makes deconstructing any data that you have on hand to feed into a function that accepts these kinds of unpacked arguments. The syntax is very similar, but is used when a function is called, not when it's defined.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">def</span> <span class="cm-def">takes_many_args</span>(<span class="cm-operator">*</span><span class="cm-variable">args</span>):
  <span class="cm-builtin">print</span>(<span class="cm-string">','</span>.<span class="cm-property">join</span>(<span class="cm-variable">args</span>))

<span class="cm-variable">long_list_of_args</span> <span class="cm-operator">=</span> [<span class="cm-number">145</span>, <span class="cm-string">"Mexico City"</span>, <span class="cm-number">10.9</span>, <span class="cm-string">"85C"</span>]

<span class="cm-comment"># We can use the asterisk "*" to deconstruct the container.</span>
<span class="cm-comment"># This makes it so that instead of a list, a series of four different</span>
<span class="cm-comment"># positional arguments are passed to the function</span>
<span class="cm-variable">takes_many_args</span>(<span class="cm-operator">*</span><span class="cm-variable">long_list_of_args</span>)
<span class="cm-comment"># Prints "145,Mexico City,10.9,85C"</span></div></span></pre>
<p>We can use the <code>*</code> when calling the function that takes a series of positional parameters to unwrap a list or a tuple. This makes it easy to provide a sequence of arguments to a function even if that function doesn't take a list as an argument. Similarly we can use <code>**</code> to destructure a dictionary.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">def</span> <span class="cm-def">pour_from_sink</span>(<span class="cm-variable">temperature</span><span class="cm-operator">=</span><span class="cm-string">"Warm"</span>, <span class="cm-variable">flow</span><span class="cm-operator">=</span><span class="cm-string">"Medium"</span>)
  <span class="cm-variable">set_temperature</span>(<span class="cm-variable">temperature</span>)
  <span class="cm-variable">set_flow</span>(<span class="cm-variable">flow</span>)
  <span class="cm-variable">open_sink</span>()

<span class="cm-comment"># Our function takes two keyword arguments</span>
<span class="cm-comment"># If we make a dictionary with their parameter names...</span>
<span class="cm-variable">sink_open_kwargs</span> <span class="cm-operator">=</span> {
  <span class="cm-string">'temperature'</span>: <span class="cm-string">'Hot'</span>,
  <span class="cm-string">'flow'</span>: <span class="cm-string">"Slight"</span>,
}

<span class="cm-comment"># We can destructure them an pass to the function</span>
<span class="cm-variable">pour_from_sink</span>(<span class="cm-operator">*</span><span class="cm-operator">*</span><span class="cm-variable">sink_open_kwargs</span>)
<span class="cm-comment"># Equivalent to the following:</span>
<span class="cm-comment"># pour_from_sink(temperature="Hot", flow="Slight")</span></div></span></pre>
<p>So we can also use dictionaries and pass them into functions as keyword arguments with that syntax. Notice that our <code>pour_from_sink()</code> function doesn't even accept arbitrary <code>**kwargs</code>. We can use this destructuring syntax even when the function has a specific number of keyword or positional arguments it accepts. We just need to be careful that the object we're destructuring matches the length (and names, if a dictionary) of the signature of the function we're passing it into.</p>
</div>

###### TASK
<p>We've got a latecomer to the new <code>create_products</code> syntax who wants to still pass in a dictionary. Unpack <code>new_product_dict</code> while passing it to <code>create_products()</code> as an argument.</p>

```python
from products import create_product

def create_products(**products_dict):
  for name, price in products_dict.items():
    create_product(name, price)

new_product_dict = {
  'Apple': 1,
  'Ice Cream': 3,
  'Chocolate': 5,
}

# Call create_product() by passing new_product_dict
# as kwargs!
create_products(**new_product_dict)


```

### Review
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>We covered a lot of ground in this lesson! We learned all about how functions can accept different arguments and different styles by which we can pass those arguments in. We covered:</p>
<ul>
<li>The default return of a function: <code>None</code></li>
<li>How to create default arguments to a function</li>
<li>How to make sure our default arguments work the way we expect when dealing with lists.</li>
<li>How to pass keyword arguments to a function</li>
<li>How to unpack multiple returns from a function</li>
<li>How to unpack multiple positional arguments to a function</li>
<li>How to unpack multiple keyword arguments to a function</li>
<li>How to pass a list as a series of arguments to a function</li>
<li>How to pass a dictionary as a series of keyword arguments to a function</li>
</ul>
<p>This is a lot, and you should be impressed with yourself! You now should be able to read many different styles of function writing in Python and come up with ways to call those functions with style and clarity. </p>
<p>Hopefully this has helped you as a writer of Python functions and enabled you to overcome any problems with input and output of a Python function you might run into. Congrats!</p>
</div>
