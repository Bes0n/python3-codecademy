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
print(type(5))
my_dict = {}
print(type(my_dict))
my_list = []
print(type(my_list))
```

### Class
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>A <em>class</em> is a template for a data type. It describes the kinds of information that class will hold and how a programmer will interact with that data. Define a class using the <code>class</code> keyword. &lt;a href="<a href="https://www.python.org/dev/peps/pep-0008/#class-names&quot;">https://www.python.org/dev/peps/pep-0008/#class-names"</a> target="_blank", rel="noopener noreferrer"&gt;PEP 8 Style Guide for Python Code  recommends capitalizing the names of classes to make them easier to identify.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">class</span> <span class="cm-def">CoolClass</span>:
  <span class="cm-keyword">pass</span></div></span></pre>
<p>In the above example we created a class and named it <code>CoolClass</code>. We used the <code>pass</code> keyword in Python to indicate that the body of the class was intentionally left blank so we don't cause an <code>IndentationError</code>. We’ll learn about all the things we can put in the body of a class in the next few exercises.</p>
</div>

###### TASK
<p>Define an empty class called <code>Facade</code>. We'll chip away at it soon!</p>

```python 
class Facade(object):
  pass
```

### Instantiation
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>A class doesn't accomplish anything simply by being defined. A class must be <em>instantiated</em>. In other words, we must create an <em>instance</em> of the class, in order to breathe life into the schematic.  </p>
<p>Instantiating a class looks a lot like calling a function.  We would be able to create an instance of our defined <code>CoolClass</code> as follows:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-variable">cool_instance</span> <span class="cm-operator">=</span> <span class="cm-variable">CoolClass</span>()</div></span></pre>
<p>Above, we created an object by adding parentheses to the name of the class. We then assigned that new instance to the variable <code>cool_instance</code> for safe-keeping. </p>
</div>

###### TASK
<p>In <strong>script.py</strong> we see our <code>Facade</code> class from last exercise. Make a <code>Facade</code> instance and save it to the variable <code>facade_1</code>.</p>

```python
class Facade:
  pass

facade_1 = Facade()
```

### Object-Oriented Programming
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>A class instance is also called an <em>object</em>. The pattern of defining classes and creating objects to represent the responsibilities of a program is known as <em>Object Oriented Programming</em> or OOP.</p>
<p>Instantiation takes a class and turns it into an object, the <code>type()</code> function does the opposite of that. When called with an object, it returns the class that the object is an instance of.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-builtin">print</span>(<span class="cm-builtin">type</span>(<span class="cm-variable">cool_instance</span>))
<span class="cm-comment"># prints "&lt;class '__main__.CoolClass'&gt;"</span></div></span></pre>
<p>We then print out the <code>type() of cool_instance</code> and it shows us that this object is of type <code>__main__.CoolClass</code>. </p>
<p>In Python <code>__main__</code>  means "this current file that we're running" and so one could read the output from <code>type()</code> to mean  "the class <code>CoolClass</code> that was defined here, in the script you're currently running."</p>
</div>

###### TASK
* <p>In <strong>script.py</strong> we see <code>facade_1</code> from last exercise. Try calling <code>type()</code> on <code>facade_1</code> and saving it to the variable <code>facade_1_type</code>.</p>

* <p>Print out <code>facade_1_type</code>.</p>

```python 
class Facade:
  pass

facade_1 = Facade()
facade_1_type = type(facade_1)
print(facade_1_type)
``` 

### Class Variables
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>When we want the same data to be available to every instance of a class we use a <em>class variable</em>. A class variable is a variable that's the same for every instance of the class. </p>
<p>You can define a class variable by including it in the indented part of your class definition, and you can access all of an object's class variables with <code>object.variable</code> syntax.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">class</span> <span class="cm-def">Musician</span>:
  <span class="cm-variable">title</span> <span class="cm-operator">=</span> <span class="cm-string">"Rockstar"</span>

<span class="cm-variable">drummer</span> <span class="cm-operator">=</span> <span class="cm-variable">Musician</span>()
<span class="cm-builtin">print</span>(<span class="cm-variable">drummer</span>.<span class="cm-property">title</span>)
<span class="cm-comment"># prints "Rockstar"</span></div></span></pre>
<p>Above we defined the class <code>Musician</code>, then instantiated <code>drummer</code> to be an object of type <code>Musician</code>. We then printed out the drummer's <code>.title</code> attribute, which is a class variable that we defined as the string "Rockstar". </p>
<p>If we defined another musician, like <code>guitarist = Musician()</code> they would have the same <code>.title</code> attribute.</p>
</div>

###### TASK
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>You are digitizing grades for <em>Jan van Eyck High School and Conservatory</em>. At <em>Jan van High</em>, as the students call it, <code>65</code> is the minimum passing grade.</p>
<p>Create a <code>Grade</code> class with a class attribute <code>minimum_passing</code> equal to <code>65</code>.</p>
</div>

```python
class Grade:
  minimum_passing = 65
```

### Methods
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p><em>Methods</em> are functions that are defined as part of a class. The first argument in a method is always the object that is calling the method. Convention recommends that we name this first argument <code>self</code>. Methods always have at least this one argument. </p>
<p>We define methods similarly to functions, except that they are indented to be part of the class.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">class</span> <span class="cm-def">Dog</span>():
  <span class="cm-variable">dog_time_dilation</span> <span class="cm-operator">=</span> <span class="cm-number">7</span>

  <span class="cm-keyword">def</span> <span class="cm-def">time_explanation</span>(<span class="cm-variable-2">self</span>):
    <span class="cm-builtin">print</span>(<span class="cm-string">"Dogs experience {} years for every 1 human year."</span>.<span class="cm-property">format</span>(<span class="cm-variable-2">self</span>.<span class="cm-property">dog_time_dilation</span>))

<span class="cm-variable">pipi_pitbull</span> <span class="cm-operator">=</span> <span class="cm-variable">Dog</span>()
<span class="cm-variable">pipi_pitbull</span>.<span class="cm-property">time_explanation</span>()
<span class="cm-comment"># Prints "Dogs experience 7 years for every 1 human year."</span></div></span></pre>
<p>Above we created a <code>Dog</code> class with a <code>time_explanation</code> method that takes one argument, <code>self</code>, which refers to the object calling the function. We created a <code>Dog</code> named <code>pipi_pitbull</code> and called the <code>.time_explanation()</code> method on our new object for Pipi.</p>
<p>Notice we didn't pass any arguments when we called <code>.time_explanation()</code>, but were able to refer to <code>self</code> in the function body. When you call a method it automatically passes the object calling the method as the first argument.</p>
</div>

###### TASK 
* <p>At <em>Jan van High</em>, the students are constantly calling the school rules into question. Create a <code>Rules</code> class so that we can explain the rules.</p>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Give <code>Rules</code> a method <code>washing_brushes</code> that returns the string .</p>
<pre><span language="md" class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined"><div class="CodeMirror">"Point bristles towards the basin while washing your brushes."</div></span></pre></div>

```python 
class Rules():
  def washing_brushes(self):
    return "Point bristles towards the basin while washing your brushes."
```

### Methods with Arguments
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Methods can also take more arguments than just <code>self</code>:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">class</span> <span class="cm-def">DistanceConverter</span>:
  <span class="cm-variable">kms_in_a_mile</span> <span class="cm-operator">=</span> <span class="cm-number">1.609</span>
  <span class="cm-keyword">def</span> <span class="cm-def">how_many_kms</span>(<span class="cm-variable-2">self</span>, <span class="cm-variable">miles</span>):
    <span class="cm-keyword">return</span> <span class="cm-variable">miles</span> <span class="cm-operator">*</span> <span class="cm-variable-2">self</span>.<span class="cm-property">kms_in_a_mile</span>

<span class="cm-variable">converter</span> <span class="cm-operator">=</span> <span class="cm-variable">DistanceConverter</span>()
<span class="cm-variable">kms_in_5_miles</span> <span class="cm-operator">=</span> <span class="cm-variable">converter</span>.<span class="cm-property">how_many_kms</span>(<span class="cm-number">5</span>)
<span class="cm-builtin">print</span>(<span class="cm-variable">kms_in_5_miles</span>)
<span class="cm-comment"># prints "8.045"</span></div></span></pre>
<p>Above we defined a <code>DistanceConverter</code> class, instantiated it, and used it to convert 5 miles into kilometers. Notice again that even though <code>how_many_kms</code> takes two arguments in its definition, we only pass <code>miles</code>, because <code>self</code> is implicitly passed (and refers to the object <code>converter</code>).</p>
</div>


###### TASK
* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>It's March 14th (known in some places as <strong>Pi day</strong>) at <em>Jan van High</em>, and you're feeling awfully festive. You decide to create a program that calculates the area of a circle.</p>
<p>Create a <code>Circle</code> class with class variable <code>pi</code>. Set <code>pi</code> to the approximation <code>3.14</code>.</p>
</div>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Give <code>Circle</code> an <code>area</code> method that takes two parameters: <code>self</code> and <code>radius</code>.</p>
<p>Return the area as given by this formula:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-variable">area</span> <span class="cm-operator">=</span> <span class="cm-variable">pi</span> <span class="cm-operator">*</span> <span class="cm-variable">radius</span> <span class="cm-operator">*</span><span class="cm-operator">*</span> <span class="cm-number">2</span></div></span></pre>
</div>

* <p>Create an instance of <code>Circle</code>. Save it into the variable <code>circle</code>.</p>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>You go to measure several circles you happen to find around. </p>
<ul>
<li>A medium pizza that is 12 inches across.</li>
<li>Your teaching table which is 36 inches across.</li>
<li>The Round Room auditorium, which is 11,460 inches across.</li>
</ul>
<p>You save the areas of these three things into <code>pizza_area</code>, <code>teaching_table_area</code>, and <code>round_room_area</code>.</p>
<p>Remember that the <code>radius</code> of a circle is half the diameter. We gave three diameters here, so halve them before you calculate the given circle's area.</p>
</div>


```python
class Circle():
  pi = 3.14
  def area(self, radius):
    return self.pi * radius ** 2
  
circle = Circle()

pizza_radius = 12/2
teaching_table_radius = 36/2
round_room_radius = 11460/2

pizza_area = circle.area(pizza_radius)
teaching_table_area = circle.area(teaching_table_radius)
round_room_area = circle.area(round_room_radius)
```

### Constructors
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>There are several methods that we can define in a Python class that have special behavior. These methods are sometimes called "magic", because they behave differently from regular methods. Another popular term is <em>dunder methods</em>, so-named because they have two underscores (double-underscore abbreviated to "dunder") on either side of them.</p>
<p>The first dunder method we're going to use is the <code>__init__</code> method (note the two underscores before and after the word "init"). This method is used to <em>initialize</em> a newly created object. It is called every time the class is instantiated.</p>
<p>Methods that are used to prepare an object being instantiated are called <em>constructors</em>. The word "constructor" is used to describe similar features in other object-oriented programming languages but programmers who refer to a constructor in Python are usually talking about the <code>__init__</code> method.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">class</span> <span class="cm-def">Shouter</span>:
  <span class="cm-keyword">def</span> <span class="cm-def">__init__</span>(<span class="cm-variable-2">self</span>):
    <span class="cm-builtin">print</span>(<span class="cm-string">"HELLO?!"</span>)

<span class="cm-variable">shout1</span> <span class="cm-operator">=</span> <span class="cm-variable">Shouter</span>()
<span class="cm-comment"># prints "HELLO?!"</span>

<span class="cm-variable">shout2</span> <span class="cm-operator">=</span> <span class="cm-variable">Shouter</span>()
<span class="cm-comment"># prints "HELLO?!"</span></div></span></pre>
<p>Above we created a class called <code>Shouter</code> and every time we create an instance of <code>Shouter</code> the program prints out a shout. Don't worry, this doesn't hurt the computer at all.</p>
<p>Pay careful attention to the instantiation syntax we use. <code>Shouter()</code> looks a lot like a function call, doesn't it? If it's a function, can we pass parameters to it? We absolutely can, and those parameters will be received by the <code>__init__</code> method.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">class</span> <span class="cm-def">Shouter</span>:
  <span class="cm-keyword">def</span> <span class="cm-def">__init__</span>(<span class="cm-variable-2">self</span>, <span class="cm-variable">phrase</span>):
    <span class="cm-comment"># make sure phrase is a string</span>
    <span class="cm-keyword">if</span> <span class="cm-builtin">type</span>(<span class="cm-variable">phrase</span>) <span class="cm-operator">==</span> <span class="cm-builtin">str</span>:

      <span class="cm-comment"># then shout it out</span>
      <span class="cm-builtin">print</span>(<span class="cm-variable">phrase</span>.<span class="cm-property">upper</span>())

<span class="cm-variable">shout1</span> <span class="cm-operator">=</span> <span class="cm-variable">Shouter</span>(<span class="cm-string">"shout"</span>)
<span class="cm-comment"># prints "SHOUT"</span>

<span class="cm-variable">shout2</span> <span class="cm-operator">=</span> <span class="cm-variable">Shouter</span>(<span class="cm-string">"shout"</span>)
<span class="cm-comment"># prints "SHOUT"</span>

<span class="cm-variable">shout3</span> <span class="cm-operator">=</span> <span class="cm-variable">Shouter</span>(<span class="cm-string">"let it all out"</span>)
<span class="cm-comment"># prints "LET IT ALL OUT"</span></div></span></pre>
<p>Above we've updated our <code>Shouter</code> class to take the additional parameter <code>phrase</code>. When we created each of our objects we passed an argument to the constructor. The constructor takes the argument <code>phrase</code> and, if it's a string, prints out the all-caps version of <code>phrase</code>.</p>
</div>



###### TASK
* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Add a constructor to our <code>Circle</code> class.</p>
<p>Since we seem more frequently to know the diameter of a circle, it should take the argument <code>diameter</code>.</p>
<p>It doesn't need to do anything yet, just write <code>pass</code> in the body of the constructor.</p>
</div>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Now have the constructor print out the message <code>"New circle with diameter: {diameter}"</code> when a new circle is created.</p>
<p>Create a circle <code>teaching_table</code> with diameter 36.</p>
</div>

```python
class Circle:
  pi = 3.14
  
  # Add constructor here:
  def __init__(self,diameter):
    print("New circle with diameter: {}".format(diameter))  
  
teaching_table = Circle(36)  
```

